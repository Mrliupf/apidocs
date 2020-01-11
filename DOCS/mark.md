## 高级搜备注	
	易贸搜原平台y-贸通高级搜和搜采购商
			加粗包含进口、出口
			不加粗是进口
			下划线包含进出口

			{"query":{"bool":{"filter":{"bool":{"must":[{"range":{"regdate":{"format":"yyyy-MM-dd","gte":"2018-11-26","lte":"2019-11-26"}}}]}},"must":[{"match":{"productdetail":{"query":"LED LLC","operator":"and"}}},{"prefix":{"hscode":{"value":"853"}}},{"exists":{"field":"origexporterid"}}]}},"size":100000}


	企业搜原平台y-贸通全库搜的按公司搜

	一键搜原平台y-贸通全库搜的按产品搜







## 获取所有节点
	/_cat/nodes?v
		


## 列出所有索引
	/_cat/indices?v
		green open trade      x0C-oYsVR0OKPj2xw0ahbg 5 1 1730896803 23578720 381.4gb 190.7gb   
		green open mycompany  1AeaZej0SiCkFnujCR2xxg 5 1  21894220  1879946  49.6gb  24.8gb   
		green open .kibana    iDpvPodCTRGp6iZklnYLmA 1 1         3        0  30.6kb  15.3kb
		green open trade_2019 sFQ5-_sWTiC_I2uK6Vp4vg 7 1 206622872 49926991 589.8gb 295.2gb
		green open trade_sea  UepdS56-S2u0NRyxW0nA3w 5 1  17585231      188  47.2gb  23.6gb
		green open trade_2018 qlD3QOorT5-6h8tF3FwI9Q 7 1 245203269 43368143 587.8gb 293.9gb
		green open trade_2017 jKlUirdNR8SAicQr-qLtlg 6 1 225008404 39420251 528.2gb 264.1gb
		green open coms       Xa8nctQGSKmKG0Bpr_3UMA 5 1  13345858  7488984  14.1gb   7.1gb

## 请求
	1、multi-index和multi-type搜索模式
	大白话解释：一次性搜索多个index和多个type下的数据

	（1）/_search：搜有索引，所有type下的所有数据都搜索出来。
	GET /_search
	（2）/index1/_search：指定一个index，搜索其下所有type的数据
	GET /test_index/_search
	（3）/index1,index2/_search：同时搜索两个index下的数据
	GET /test_index,ecommerce/_search
	（4）/1,2/_search：按照通配符去匹配多个索引
	GET /test_*,*rce/_search
	（5）/index1/type1/_search：搜索一个index下指定的type数据
	GET /test_index/test_type/_search
	（6）/index1/type1,type2/_search：可以搜索一个index下多个type的数据
	GET /test_index/test_type1,test_type2/_search
	（7）/index1,index2/type1,type2/_search搜索多个index下的多个type数据
	GET /test_index,ecommerce/test_index,product/_search
	（8）/all_type1,type2/_search：_all可以代表搜索所有index下的指定type数据
	GET /_all/test_index,product/_search
	链接：https://www.jianshu.com/p/8494a1106619

## 结果字段说明
	took：耗费了几毫秒


	timed_out：是否超时

	_shards：数据拆成5个分片，对于搜索请求，会打到所有的primary shard（或者是它的某个replica shard也可以），所以total和successful会是5；
	hits：查询的所有结果
	hits里面的 total：查询结果的数量（多少个 document）
	max_score：score的含义就是document对于一个search的相关度的匹配分数，越相关、就越匹配，分数也越高；
	hits.hits（hits里面包含了hits）：包含了匹配搜索的document的详细数据-----里面的hits包含的是和每个文档相关的数据，外面的hits有的数据是统计数据，如total等--------一般都有两个hits嵌套；
	_index：该文档所属的index
	_type：该文档所属的type
	_id：该文档的id
	_source：具体的内容，即存储的json串
	————————————————
	版权声明：本文为CSDN博主「夜-NULL」的原创文章，遵循 CC 4.0 BY-SA 版权协议，转载请附上原文出处链接及本声明。
	原文链接：https://blog.csdn.net/qq_33999844/article/details/82987537


## 查询实列 1

	http://39.100.97.53:9200/trade_2018,trade_2019/_search
		trade 索引（数据库）

		{
		   "query":{"match":{"buyername":"AA FLORIDA PALLET INC"}},//搜索条件
		    "size":2,//每页显示大小
		    "from":10,//页码
		   "sort":{"regdate":{"order":"desc"}},//排序
		    "_source":["buyername","tradeno"]//获取列
		}	
{
    "query":{
        "bool":{
            "must":[
                {
                    "match":{
                        "buyername":"ALKVISUAL"
                    }
                },
                {
                    "match":{
                        "buyername":"LED"
                    }
                },
                {
                    "match":{
                        "buyername":"DISPLAY"
                    }
                },
                {
                    "match":{
                        "buyername":"SOLUTIONS"
                    }
                }
            ],
            "filter":{
                "range":{
                    "regdate":{
                        "gte":"2018-11-20",
                        "lte":"2019-11-20",
                        "format":"yyyy-MM-dd"
                    }
                }
            }
        }
    },
"aggs" : {
        "buyername" : {
            "terms" :{ "script" : {
                    "inline": "doc['importerid.keyword'].value +'|'+ doc['buyername.keyword'].value+'|'+doc['importercountry.keyword'].value",
                    "lang": "painless"
                }}
        }
    }
}


	doc_count_error_upper_bound 未知
	sum_other_doc_count 当有大量不同值时，ES只返回数量最多的项。这个数字表示有多少文档的统计数量没有返回。
	默认情况，对于某一项的聚合，只会返回数量最高的10项，通过调整size参数，可以控制默认的行为。
	我测试到，令size=0时候，会返回所有的项。

	Size
	size参数用来指定在列表中返回多少项。如果该项的值的个数要大于这个size ，那么返回的结果可能会不准确，有轻微的误差。甚至文档数最多的那个值没有的返回。

	文档的数量是大约的量
	文档的数量是不准确的，只是一个大概值。因为每个分片给出它排好的前n的部分，然后再把各个分片的结果联合成最后的结果。
	官方文档给了一个非常好的例子，还有几张表格，说明造成这个情况的原因。可以自己跳过去阅读以下就明白了。这一切的原因都是因为 ES是一个分布式的存储方式。

	Shard size
	取得size的值越大，结果会越接近准确，当然这样导致的负载也会越高（因为更多的查询和节点之间大数据量的传输）。
	默认shard_size是等于size的。如果shard_size 取更大的值，结果会更准确。

	计算文档数错误

	有两个错误值会显示在项的聚合上，第一个doc_count_error_upper_bound ，给出个没有被算进最后的结果的最大可能的数字。这个表明在最坏情况下，有doc_count_error_upper_bound 这么多文档个数的一个值被遗漏了。 这就是doc_count_error_upper_bound （文档数错误上界）这个参数的意义。

	每个桶里的错误数
	如果设置show_term_doc_count_error这个参数为ture，还会对每个 bucket都显示一个错误数，表示最大可能的误差情况。

	而且，如果不是按照排序的话，这个错误是算不出来的，这时候，会给一个-1来表示这种有错，但是不知道错误边界的情况。

	Order
	用order参数可以做排序，默认是按照doc_count倒序排列的。
	可以改变默认情况
	“order” : { “_count” : “asc” } 这是按照doc_count升序排列
	“order” : { “_term” : “asc” } 这是按照字母表升序排列。


	doc_count_error_upper_bound：表示没有在这次聚合中返回、但是可能存在的潜在聚合结果，这里的值为 3，表除去red、blue和green之外，还可能有一个聚合结果为 3。从返回结果看，可能会排在第二名。
	sum_other_doc_count：表示这次聚合中没有统计到的文档数。因为ES为分布式部署，不同文档分散于多个分片，这样当聚合时，会在每个分片上分别聚合，然后由协调节点汇总结果后返回。这里因为请求的是排名前三的聚合，所以每个分片只聚合了本分片中排名前三的color。其他没有统计到的文档数由每个节点返回后，汇总为此元素。这里值为 10，表示有10个文档没有参与此次聚合。
	popular_colors：聚合结果，默认由高到低排列。key表示聚合元素的值，doc_count表示元素出现的次数。注意，这里的doc_count也是不准确的。

	作者：奕_然
	链接：https://www.jianshu.com/p/f650f76f21e2
	来源：简书
	著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

## 查询实列 2
			{
	    "query":{
	        "bool":{
	            "filter":[
	                {
	                    "match":{
	                        "buyername":{
	                            "query":"led"
	                        }
	                    }
	                },
	                {
	                    "range":{
	                        "regdate":{
	                            "gte":"2018-11-19",
	                            "lt":"2019-11-19"
	                        }
	                    }
	                }
	            ]
	        }
	    },
	    "_source":[
	        "buyername",
	        "regdate",
	        "productdetail",
	        "suppliername",
	        "origincountry",
	        "destcountry",
	        "salecountry"
	     ]
	   }	

## 聚合查询
		{
	    "query":{
	        "bool":{
	            "should":[
	                {
	                    "match_phrase_prefix":{
	                       "buyername":{"query":"LED","slop":3,"max_expansions":60}
	                    }
	                },
	                {
	                    "match_phrase_prefix":{ 
	                       "suppliername":{"query":"LED","slop":3,"max_expansions":60}
	                    }
	                },
	                {
	                    "match_phrase_prefix":{ 
	                       "productdetail":{"query":"LED","slop":3,"max_expansions":60}
	                    }
	                }
	            ],
	      "minimum_should_match": 2,
	            "filter":{
	                "range":{
	                    "regdate":{
	                        "gte":"2019-11-13",
	                        "lte":"2019-11-20",
	                        "format":"yyyy-MM-dd"
	                    }
	                }
	            }
	        }
	    },
	"aggs" : {
	        "buyername" : {
	            "terms" :{ "script" : {
	                    "inline": "doc['importerid.keyword'].value +'|'+ doc['buyername.keyword'].value+'|'+doc['importercountry.keyword'].value",
	                    "lang": "painless"
	                },"size":20}
	        }
	    }
	    }



## 查询实列 3
			{
	    "query":{
	        "bool":{
	 "should":[
	                   { "match":{ "buyername": "led"}},
	                   { "match":{ "suppliername": "led"}}
	                ],
	            "filter":[
	                
	                {
	                    "range":{
	                        "regdate":{
	                            "gte":"2018-11-19",
	                            "lt":"2019-11-19"
	                        }
	                    }
	                }
	            ]
	        }
	    },
	    "_source":[
	        "buyername",
	        "regdate",
	        "productdetail",
	        "suppliername",
	        "origincountry",
	        "destcountry",
	        "salecountry"
	    ]
	}	

## 函数
		   gte：　　大于或等于
	　　　　gt：　　 大于
	　　　　lte：　　小于或等于
	　　　　lt：　　   小于
		https://www.cnblogs.com/shaosks/p/7810046.html

		match 询问
		用于执行全文查询的标准查询，包括模糊匹配和短语或接近查询。
		match_phrase 询问
		与match查询类似，但用于匹配确切的短语或单词接近匹配。
		match_phrase_prefix 询问
		穷人按你的类型搜寻。与match_phrase查询类似，但是对最后一个单词进行通配符搜索。
		multi_match 询问
		match查询的多字段版本。
		common_terms 询问
		一个更专业的查询，它对不常见的单词给予更多的偏爱。
		query_string 询问
		支持紧凑的Lucene 查询字符串语法，允许您在单个查询字符串中指定AND | OR | NOT条件和多字段搜索。仅限于专业用户。
		simple_query_string
		query_string适用于直接向用户公开的语法的更简单，更可靠的版本。

		{
			"bool":{
				    "must"        : [],
				    "should"   : [],
				    "must_not" : [],
				}
		}
		#must:条件必须满足,相当于sql语句的and
		#should:条件可以满足也可以不满足,相当于sql语句的or
		#must_not:条件不需要满足,相当于sql语句的not


## 时间和查询并列
 		
			{
			    "query":{
			        "bool":{

				            "filter":{
				                    "range":{
				                        "regdate":{
				                            "gte":"2019-11-13",
				                            "lt":"2019-11-19"
				                        }
				                    }},

				       "should":[
				                   { "match":{ "buyername": "led"}},
				                   { "match":{ "suppliername": "led"}}
				                ]
			                }
					    },
					"size":2
			}	









	match_phrase_prefix 用法（不常用），一般用于类似 Google 搜索框，关键字输入推荐
	max_expansions 用来限定最多匹配多少个 term，优化性能
	但是总体来说性能还是很差，因为还是会扫描整个倒排索引。推荐用 edge_ngram 做该功能

			{
    "query":{
        "bool":{
            "should":[
                {
                    "match_phrase_prefix":{
                       "buyername":{"query":"LED","max_expansions": 60}
                    }
                },
                {
                    "match_phrase_prefix":{ 
                       "suppliername":{"query":"LED","max_expansions": 60}
                    }
                }
            ],
      "minimum_should_match": 1,
            "filter":{
                "range":{
                    "regdate":{
                        "gte":"2019-11-13",
                        "lte":"2019-11-20",
                        "format":"yyyy-MM-dd"
                    }
                }
            }
        }
    },
    "size":29
    }


prefix 前缀搜索（性能较差，扫描所有倒排索引）





通配符搜索（性能较差，扫描所有倒排索引）
{
    "query":{
        "bool":{
            "should":[
                {
                    "wildcard":{
                       "buyername":{"value":"*led*"}
                    }
                },
                {
                    "wildcard":{ 
                       "suppliername":{"value":"*led*"}
                    }
                }
            ],
      "minimum_should_match": 1,
            "filter":{
                "range":{
                    "regdate":{
                        "gte":"2019-11-13",
                        "lte":"2019-11-20",
                        "format":"yyyy-MM-dd"
                    }
                }
            }
        }
    },
    "size":29
    }






        userid 用户id
		country 国家编码
		inout   进出口  进口（import）/出口(export)
		startdate 开始时间
		enddate  结束时间
		billno 提单号
		notifyname  通知人
		hscode hs编码
		buyername 采购商
		suppliername 供应商
		prodesc 商品描述
		origincountry 原产国
		preciselyquery 精确查找 采购商(buyer)/供应商(supplier)
		marksnumbers 唛头
		container 集装箱号
		destinationcountry 目的国
		brand  品牌名称
		manufacturer 制造商
		salecountry 出口国
		customs 关区
		filterword 筛选
		pageindex 页码
		pagesize 每页显示数据




## 文档样例
		{
		 "tradeno": "D05AC788A6344A6DAA478DAFA243B14D",            提单号
          "origimporterid": "EC91A4B0A4BF4B07834625968CA010C3",    原始采购商id
          "importerid": "735F5EDDE1C14B4C8AE53DA794A665AD",       采购商id
          "origexporterid": "5B853FC0FD5C4BC9BF440611ED99065C",    原始供应商id
          "exporterid": "9CCEED4555614E87AF0468276B0A4B81",      供应商id
          "inout": "import",              进出口
          "source": "US",              数据源
          "regdate": "2019-07-30",     日期	
          "hscode": "200979",          HS编码	
          "productdetail": "ORGANIC APPLE JUICE CONCENTRATE",   商品描述	
          "customs": null,            关区
          "manufacturer": null,            制造商
          "portorigin": "VALENCIA",        起运港
          "portdest": "LONG BEACH",         卸载港口
          "origincountry": "JP, JAPAN",           产国
          "destcountry": null,      目的国
          "salecountry": null,           出口国       
          "blnumber": "BARSMELG19401719",  提单号	
          "notifyparty": "ELDINAR GIDA MADDELERI",     通知人名称	
          "notifypartyaddress": "ITH IHR TIC VE SAN A S CIVRIL YOLU CD 3 KM DINAR ",      通知人地址	
          "brand": null,                  品牌
          "containerid": "SZLU9484402",     集装箱号	
          "marksnumbers": "ORGANIC APPLE JUICE CONCENTRATE",  唛头描述	
          "count": 96,  数量
          "money": 0,    金额
          "weight": 28128,  重量
          "buyername": "EZ PORT CORP",     采购商
          "suppliername": "ELDINAR GIDA MADDELERI",  供应商	
          "importercountry": "US",         采购商国家
          "exportercountry": "JP",         供应商国家
          "buyeraddress": "65 HORRISTOWN RD STE#304B ",   采购商地址   	 
          "supplieraddress": "ITH IHR TIC VE SAN A S CIVRIL YOLU CD 3 KM DINAR ",     供应商地址	 	
          "rawimporter": "EZ PORT CORP.",           	 原始采购商
          "rawexporter": "ELDINAR GIDA MADDELERI"     原始供应商	
		}



##    yyit.site.tradecenter ->CompanyContacter2  联系人限制
       详情页 查询限制

      tradeno 
