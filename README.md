## 1px Border Demo ##

>ios7下1px线的几种实现方式

- [1px-1.html](http://songxc.github.io/1px/1px-1.html '1px Border Demo') (background-color + scaleY)

		.list li {
			position: relative;
			font-size: 16px;
			font-weight: bold;
			padding: 15px;
			-webkit-box-sizing: border-box;
			background: -webkit-linear-gradient(top, #fafafa 0%, #f9f9f9 50%, #fafafa 100%);
		}
		
		.list li::after {
			content: '';
			position: absolute;
			left: 0;
			background: #aaa;
			width: 100%;
			height: 1px;
			-webkit-transform: scaleY(0.5);
		}
		
		.list li::after {
			bottom: 0;
			-webkit-transform-origin: 0 bottom;
		}

- [1px-2.html](http://songxc.github.io/1px/1px-2.html '1px Border Demo') (border + scale)
	
		.list li {
	    	position: relative;
	        display: inline-block;
	        width: 140px;
	        padding: 20px 0;
	        font-size: 16px;
	        font-weight: bold;
	        margin: 0 10px 10px 0;
	        -webkit-border-radius: 5px;
	    	-webkit-box-sizing: border-box;
	    	background: -webkit-linear-gradient(top, #fafafa 0%, #f0f0f0 50%, #fafafa 100%);
	    }
	
	    .list li::after {
			content: '';
	        position: absolute;
	        top: 0;
	        left: 0;
	        width: 200%;
	        height: 200%;
	        border: 1px solid #aaa;
	        -webkit-border-radius: 10px;
	        -webkit-box-sizing: border-box;
	        -webkit-transform: scale(0.5);
	        -webkit-transform-origin: left top;
	    }

- [1px-3.html](http://songxc.github.io/1px/1px-3.html '1px Border Demo') (background)

		.list li {
	    	position: relative;
	        display: inline-block;
	        width: 140px;
	        padding: 20px 0;
	        font-size: 16px;
	        font-weight: bold;
	        text-align: center;
	        margin: 0 10px 10px 0;
	        border: 1px solid #fff;
	    	-webkit-box-sizing: border-box;
	    	background: -webkit-linear-gradient(top, #fafafa 0%, #f0f0f0 50%, #fafafa 100%);
	    }
	
	    .list li::after {
	        content: '';
	        position: absolute;
	        top: 0;
	        left: 0;
	        width: 100%;
	        height: 100%;
	        background-image: -webkit-linear-gradient(top, #aaa, #aaa 40%, transparent 40%, transparent),
	            -webkit-linear-gradient(right, #aaa, #aaa 40%, transparent 40%, transparent),
	            -webkit-linear-gradient(bottom, #aaa, #aaa 40%, transparent 40%, transparent),
	            -webkit-linear-gradient(left, #aaa, #aaa 40%, transparent 40%, transparent);
	        background-size: 100% 1px, 1px 100%;
	        background-position: top, right top, bottom, left top;
	        background-repeat: no-repeat;
	    }
