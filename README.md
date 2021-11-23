# Portfolio Scheduler

일정을 추가,조회,삭제,수정할 수 있는 스케쥴러 입니다. <br><br>


<img src="https://user-images.githubusercontent.com/86813319/143006028-163333b0-241a-47bd-a6d3-b72d60012403.png" width="600" height = "310">

실제 구현된 모습을 보고 싶다면 [여기](http://hamilkarr2.cafe24app.com) 를 클릭하세요.

## Used Skill Set and Development Tool
- **JavaScript (ES2016++)** 
  - jQuery
  - Axios
- **node.js**
- **MySQL 8.0**
- Visual Studio Code

### 주요 기능
  - node.js
    - sequelize : DB와의 연동.  <br>
      models\scheduler.js <br>
    
```js
delete : async function (period, color) {
		if (!period || !color) 
			return false;
		
		try {
			const sql = "DELETE FROM schedule WHERE period = ? AND color = ?";
			await sequelize.query(sql, {
				replacements : [period, color],
				type : QueryTypes.DELETE,
			});
		
			return true;
		} catch (err) {
			logger(err.message, 'error');
			logger(err.stack, 'error');
			return false;
		}
	},
```

  - nunjucks : html에서 반복,조건, 제어문 등을 사용해 코드의 간결함과 효율성을 높임. <br>
    views\ _main.html 

```html
	<ul class='yoils'>
	{% for yoil in yoilsEn %}
		<li>{{ yoil }}</li>
	{% endfor %}
	</ul>
```

 

    
  




