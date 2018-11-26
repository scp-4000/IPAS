https://goo.gl/wXpBbL

https://drive.google.com/drive/folders/0B-wQltXzv1wFMWhKUFM2QXVveDQ

```
7天學會大數據資料處理—NoSQL：MongoDB入門與活用(第二版)
書號：MP21722	作者：黃士嘉、吳佩儒 著	ISBN： 978-986-434-233-4
定價：NT$400元	印刷：單色	頁數：224頁
書籍規格：17*23	上市日：2017/8/2

http://www.drmaster.com.tw/Bookinfo.asp?BookID=MP21722
```

```
快速具備MongoDB的基本使用技能
活用大數據資料處理的實用入門書！

◎內容精簡、淺顯易懂，可7天快速學會MongoDB
◎搭配Robo 3T的圖形介面操作，一步步帶領你上手
◎透過實際範例，準確掌握精髓技巧

在大數據時代，NoSQL已經成為資料儲存的主流，
而在NoSQL中最具影響力的資料庫，則以文件類型的MongoDB為第一，其在IT業界最為活躍。
本書內容共分為7章，可以讓你在短時間內快速上手，了解如何將MongoDB實際應用在真實系統產品上。
本書適合資料庫管理開發人員、資料探勘與分析人員以及各類應用大數據儲存的開發人員閱讀。
```

```
Chapter 01 介紹NoSQL
Chapter 02 安裝MongoDB資料庫與啟動服務
Chapter 03 安裝MongoDB資料庫之圖形用戶介面（GUI）與基本操作
Chapter 04 MongoDB進階功能—查詢（Find）
Chapter 05 MongoDB進階功能—新增、更新與刪除
Chapter 06 MongoDB進階功能—聚集（Map-Reduce）
Chapter 07 MongoDB應用程式範例—實作一個會員系統的Web API　
```

####  Chapter 02  MongoDB資料庫安裝與啟動服務

### Chapter 03 安裝MongoDB資料庫之圖形用戶介面（GUI）與基本操作

MongoDB資料庫管理:Studio 3T vs Robo 3T(前身為Robomongo)
https://robomongo.org/download
```
{
	"profile":{"name":"林小宏","id":"108418005"},
	"course":{
		"102-1":[
			{"course_id":"179729","course_name":"專題討論(A)","credits":1},
			{"course_id":"187174","course_name":"數位影像處理","credits":3},
			{"course_id":"179746","course_name":"軟硬體共同設計","credits":3},
			{"course_id":"179787","course_name":"VLSI系統架構設計","credits":1},
			{"course_id":"187670","course_name":"高等計算機視覺","credits":3}
		]
		,"102-2":[
			{"course_id":"182495","course_name":"專題討論(A)","credits":1},
			{"course_id":"182515","course_name":"資料庫系統","credits":3},
			{"course_id":"190446","course_name":"數位電視設計","credits":3},
			{"course_id":"190517","course_name":"最佳化概論","credits":3}
		]
	}
}
{
	"profile":{"name":"劉小賓","id":"108418006"},
	"course":{
		"102-1":[
			{"course_id":"179729","course_name":"專題討論(A)","credits":1},
			{"course_id":"187174","course_name":"數位影像處理","credits":3},
			{"course_id":"187182","course_name":"互動式娛樂服務之音訊處理技術","credits":3},
			{"course_id":"187656","course_name":"職場達人-自傳履歷與面試實務","credits":1},
			{"course_id":"187670","course_name":"高等計算機視覺","credits":3}
		],
		"102-2":[
			{"course_id":"182495","course_name":"專題討論(A)","credits":1},
			{"course_id":"182515","course_name":"資料庫系統","credits":3},
			{"course_id":"190446","course_name":"數位電視設計","credits":3},
			{"course_id":"190517","course_name":"最佳化概論","credits":3}
		]
	}
}
```

### Chapter 04 MongoDB進階功能—查詢（Find）

```
{
	_id:"4-1_1",
	book:"實用英文會話",
	price:299.0, authors: ["Jason", "Mary", "Bob"],
	borrower:{
		name:"王小明",
		timestamp:ISODate("2015-07-23T12:00:00Z")
	}
}
{
	_id:"4-1_2",
	book:"七天學會大數據資料庫處理－NoSQL:MongoDB入門與活用",
	price:360.0, authors: ["黃小嘉"],
	borrower:{name:"王小明", timestamp:ISODate("2015-07-24T12:30:00Z")}
}
{
	_id:"4-1_3",
	book:"日本環球影城全攻略",
	price:280, authors: ["Jason", "Mary", "Bob"]
}

```


```
{
	_id:"4-2_1",
	members: [ "Jason", "Bob" ],
	messages: [ 
		{ sender:"Jason", content:"Hello"},
		{ sender:"Bob", content:"Hi"},
		{ sender:"Jason", content:"午餐要吃什麼"},
		{ sender:"Jason", content:"吃義大利麵!?"},
		{ sender:"Bob", content:"走阿"}
	]
}
{_id:"4-2_2", members:[ "Jason", "Mary" ], messages:[]}
{_id:"4-2_3", members:[ "Bob", "Mary" ], messages:[]}

```


```
{
	_id:"4-3_1",
	name:"中山女中",
	location: { type: "Point", coordinates: [ 121.537034, 25.048499 ] } 
}
{
	_id:"4-3_2",
	name:"國立台北商業大學",
	location: { type: "Point", coordinates: [ 121.525256, 25.042267 ] } 
}
{
	_id:"4-3_3",
	name:"行政院",
	location: { type: "Point", coordinates: [ 121.520958, 25.046316 ] } 
}
{
	_id:"4-3_4",
	name:"國立台灣博物館", location: { type: "Point", coordinates: [ 121.514940, 25.042751 ] }
}

```


```
{_id:"4-4_1", name: "A", location: { type: "Point", coordinates: [ 1, 2 ] } }
{_id:"4-4_2", name: "B", location: { type: "Point", coordinates: [ 2, 2 ] } }
{_id:"4-4_3", name: "C", location: { type: "Point", coordinates: [ 2, 1 ] } }

```


```
{_id:"4-9_01", name:"江小于", age:22, phone:"0967-481-146"}
{_id:"4-9_02", name:"穆小蓉", age:18, phone:"0989-153-149"}
{_id:"4-9_03", name:"陳小昇", age:24, phone:"0955-581-064"}
{_id:"4-9_04", name:"傅小彰", age:25, phone:"0967-058-845"}
{_id:"4-9_05", name:"廖小健", age:28, phone:"0989-758-138"}
{_id:"4-9_06", name:"陳小翰", age:31, phone:"0989-051-129"}
{_id:"4-9_07", name:"鄭小瀚", age:27, phone:"0967-984-852"}
{_id:"4-9_08", name:"梁小瑋", age:21, phone:"0989-748-913"}
{_id:"4-9_09", name:"陳小鴻", age:22, phone:"0955-685-846"}
{_id:"4-9_10", name:"陳小豪", age:20, phone:"0955-648-843"}

```
### Chapter 05 MongoDB進階功能—新增、更新與刪除

```
{ _id: "001", name: "小明", balance: 1500 }
{ _id: "002", name: "小華", balance: 3200 }
{ _id: "003", name: "小花", balance: 2400 }

```


```
{ _id: "001", product: "Sony, SBH60", type: "USD", price: 76.4 }
{ _id: "002", product: "Sony, SBH70", type: "USD", price: 75.8 }
{ _id: "003", product: "Sony, SBH80", type: "NTD", price: 2980 }
```

```
{ _id: "001", studentNumber: "102418099", studentName: "小眀", score: 50}
{ _id: "002", studentId: "102418098", studentName: "小華", score: 80}
{ _id: "003", studentId: "102418097", studentName: "小花", score: 120}
```

```
{ 
	_id: "001",
	group: "臺北大車隊",
	status: "busy", 
	seatInfo: { capacity : 5, remaining: 4, riding: 1 },
	location: [121.517224, 25.047974],
	lastModified: ISODate("2015-12-12T12:00:00")
}
{
	_id: "002",
	group: "臺北大車隊",
	status: "busy",
	seatInfo: { capacity : 5, remaining: 1, riding: 4 },
	location: [121.517224, 25.047974],
	lastModified: ISODate("2015-12-14T12:00:00")
}
{
	_id: "003",
	group: "臺北大車隊",
	status: "rest",
	seatInfo: { capacity : 5, remaining: 5, riding: 0 },
	location: [121.549916, 25.050594],
	lastModified: ISODate("2015-12-02T12:00:00")
}

```

```
{ _id: "001", list: [30, 40 ,50 ] }

```

### Chapter 06 MongoDB進階功能—聚集（Map-Reduce）

```
{ city: "台北市",district: "北投", age: 25 }
{ city: "台北市",district: "士林", age: 20 }
{ city: "台北市",district: "士林", age: 30 }
{ city: "台北市",district: "大同", age: 30 }
{ city: "台北市",district: "大同", age: 40 }
{ city: "台北市",district: "大同", age: 50 }
{ city: "台北市",district: "中山", age: 15 }
{ city: "台北市",district: "中山", age: 25 }
{ city: "台北市",district: "松山", age: 18 }
{ city: "台北市",district: "松山", age: 22 }
{ city: "台北市",district: "松山", age: 35 }
{ city: "台北市",district: "松山", age: 45 }
{ city: "新北市",district: "板橋", age: 22 }
{ city: "新北市",district: "三重", age: 45 }
{ city: "新北市",district: "中和", age: 50 }
{ city: "新北市",district: "永和", age: 34 }
{ city: "新北市",district: "新莊", age: 45 }
{ city: "新北市",district: "新店", age: 14 }
{ city: "新北市",district: "土城", age: 47 }
{ city: "新北市",district: "蘆洲", age: 24 }
{ city: "新北市",district: "汐止", age: 35 }
{ city: "新北市",district: "樹林", age: 29 }
{ city: "新北市",district: "淡水", age: 43 }
{ city: "新北市",district: "鶯歌", age: 24 }

```
### Chapter 07 MongoDB應用程式範例—實作一個會員系統的Web API　

```
{
	"profile":{"name":"林小宏","id":"108418005"},
	"course":{
		"102-1":[
			{"course_id":"179729","course_name":"專題討論(A)","credits":1},
			{"course_id":"187174","course_name":"數位影像處理","credits":3},
			{"course_id":"179746","course_name":"軟硬體共同設計","credits":3},
			{"course_id":"179787","course_name":"VLSI系統架構設計","credits":1},
			{"course_id":"187670","course_name":"高等計算機視覺","credits":3}
		]
		,"102-2":[
			{"course_id":"182495","course_name":"專題討論(A)","credits":1},
			{"course_id":"182515","course_name":"資料庫系統","credits":3},
			{"course_id":"190446","course_name":"數位電視設計","credits":3},
			{"course_id":"190517","course_name":"最佳化概論","credits":3}
		]
	}
}
{
	"profile":{"name":"劉小賓","id":"108418006"},
	"course":{
		"102-1":[
			{"course_id":"179729","course_name":"專題討論(A)","credits":1},
			{"course_id":"187174","course_name":"數位影像處理","credits":3},
			{"course_id":"187182","course_name":"互動式娛樂服務之音訊處理技術","credits":3},
			{"course_id":"187656","course_name":"職場達人-自傳履歷與面試實務","credits":1},
			{"course_id":"187670","course_name":"高等計算機視覺","credits":3}
		],
		"102-2":[
			{"course_id":"182495","course_name":"專題討論(A)","credits":1},
			{"course_id":"182515","course_name":"資料庫系統","credits":3},
			{"course_id":"190446","course_name":"數位電視設計","credits":3},
			{"course_id":"190517","course_name":"最佳化概論","credits":3}
		]
	}
}

```


