## ES7-preview

### async await

> 1.不依赖于外部的runner	=>		标准统一、性能提升

> 2.可以用箭头函数

```
	//	async function readData(){
	//		let data1 = await $.ajax({url: 'data/arr.txt', dataType: 'json'});
	//		let data2 = await $.ajax({url: 'data/json.txt', dataType: 'json'});
	//	
	//		console.log(data1, data2);
	//	}
		
		let readData = async () =>{
		  let data1 = await $.ajax({url: 'data/arr.txt', dataType: 'json'});
		  let data2 = await $.ajax({url: 'data/json.txt', dataType: 'json'});
		
		  console.log(data1, data2);
		}
		
		readData();
```
