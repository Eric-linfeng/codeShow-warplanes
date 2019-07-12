## Thunder  Fighter  说明



### ###界面设计

#### 背景图片

​	./img    

#### 背景音效

​	./audio

#### 背景位移



#### 战机初始化

	##### 	战机

​		 var plane = document.createElement('div');

​       	 	plane.className = 'plane';

​        		plane.style.width = '110px';

​        		plane.style.left = (*this*.layout.offsetWidth - plane.offsetWidth) / 2 + 'px';

​      			  *this*.layout.append(plane);

​        			*this*.plane = plane;

​        			plane.itimer1 = setInterval(function () {

​            			That.createBullet(That.data.BULLET.p.name, plane, 0, 1);

​       				 }, 150);

​      			  *this*.bindPlane(plane);

​       				 plane.itimer2 = setInterval(function () {

​           				 That.createEnemy();

​      				  }, 1000)

	##### 	敌机
		土黄  分解  双翼
		

​		var e = *this*.data.eArr[~~(Math.random() * 60)];

​     		var ey = document.createElement('div');

​       		 ey.className = 'enemy enemy' + e;

​      			  ey.style.cssText = 'width:' + *this*.data.ENEMY._width[e] + 'px; height:' + *this*.data.ENEMY._height[e] + 'px';

​        		ey.style.left = ~~(Math.random() * (*this*.layout.offsetWidth - *this*.data.ENEMY._width[e])) + 'px';

​       		 ey.setAttribute('blood', *this*.data.ENEMY.blood[e]);

​     		   ey.setAttribute('score', *this*.data.ENEMY.score[e]);

​        		ey.setAttribute('speed', *this*.data.ENEMY.speed[e]);

​       		 ey.setAttribute('bullet', *this*.data.ENEMY.bullet[e]);

#### 开始游戏

​	+严格模式

​		-开始游戏

​			window.onload = function () {

  			  myGame.init();

​		-初始化

​			layout = document.getElementById('layout'),

​            		mystart = document.getElementById('start'),

​            			score = document.getElementById('score'),

​            				That = *this*;

​		-飞机的子弹参数

​			  var bt = document.createElement('div');

​        			bt.className = name;

​      				  var _p = obj;

​      				  bt.style.top = (_p.offsetTop + h - bt.offsetHeight * direction) - 10 + 'px';

​       				 // 弹道方向

​      				  bt.style.left = (_p.offsetLeft + _p.offsetWidth / 2) - 4 + 'px';

​      					  *this*.layout.append(bt);

​        					if (bt.classList.contains('b1')) {

​           					 *this*.runBullet(bt, 0, -30);

​     					   } else {

​           						 *this*.speedDecomposition(*this*.plane, bt);

​          						  *this*.runBullet(bt, *this*.vx, *this*.vy);

​     					   }

​		-子弹运动轨迹

​				   b.timer = setInterval(function () {

​         				 if (b.offsetTop <= 30 || b.offsetTop >= That.layout.offsetHeight || b.offsetLeft 						<= 0 || b.offsetLeft >= That.layout.offsetWidth) {   //限制子弹范围

​                					clearInterval(b.timer);

​              						  That.layout.removeChild(b);

​           				 } else {

​               				 b.style.cssText = 'top : ' + (b.offsetTop + y) + 'px; left : ' + (b.offsetLeft + x) + 'px';

​           				 }

​		-生成本机

​		-生成敌机（土黄   ，分解   ，双翼）（血量和获得分数！）

​		-敌机运动轨迹

​		-本机运动轨迹

​		-爆炸效果（爆炸音效）

​		-游戏结束

​				document.getElementById("fire").pause();

​        				document.getElementById('bigboom').play();

​        				clearInterval(*this*.plane.itimer2);

​        				clearInterval(*this*.plane.itimer1);

​       				 *this*.mystart.style.display = 'block';

​        				document.getElementsByClassName('score')[0].style.display = 'none';

​        				document.getElementById('name-over').getElementsByTagName('i')[0].innerHTML = 'GAME OVER!';

​        				document.getElementById('name-over').getElementsByTagName('p')[0].innerHTML = *this*.score.innerHTML;

​        				document.getElementById('startBtn').value = 'AGAIN';

​		-基本技术参数

​		





### 界面初始化![初识界面2019-06-29_19-45-33](C:\Users\12616\Desktop\黑马\作业\课堂图片\0628\初识界面2019-06-29_19-45-33.png)



### 效果界面

![效果图_2019-06-29_20-10-51](C:\Users\12616\Desktop\黑马\作业\课堂图片\0628\效果图_2019-06-29_20-10-51.png)