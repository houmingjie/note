# webpack循环依赖
## 结构
entry:app.js  
```jsx
import a from "a";
```
a.js  
```jsx
console.info(b);
export default "a";
import b from "b";//ES6标准：import会被提前
```
b.js  
```jsx
import a from "a";  
console.info(a);  
export default "b";
```

输出  
```jsx
    undefined;
    b;
```


## 打包结果
```jsx
/******/ (function(modules) { // webpackBootstrap
/******/ 	// The module cache
/******/ 	var installedModules = {};
/******/
/******/ 	// The require function
/******/ 	function __webpack_require__(moduleId) {
/******/
/******/ 		// Check if module is in cache
/******/ 		if(installedModules[moduleId])
/******/ 			return installedModules[moduleId].exports;
/******/
/******/ 		// Create a new module (and put it into the cache)
/******/ 		var module = installedModules[moduleId] = {
/******/ 			exports: {},
/******/ 			id: moduleId,
/******/ 			loaded: false
/******/ 		};
/******/
/******/ 		// Execute the module function
/******/ 		modules[moduleId].call(module.exports, module, module.exports, __webpack_require__);
/******/
/******/ 		// Flag the module as loaded
/******/ 		module.loaded = true;
/******/
/******/ 		// Return the exports of the module
/******/ 		return module.exports;
/******/ 	}
/******/
/******/
/******/ 	// expose the modules object (__webpack_modules__)
/******/ 	__webpack_require__.m = modules;
/******/
/******/ 	// expose the module cache
/******/ 	__webpack_require__.c = installedModules;
/******/
/******/ 	// __webpack_public_path__
/******/ 	__webpack_require__.p = "/dist/";
/******/
/******/ 	// Load entry module and return exports
/******/ 	return __webpack_require__(0);
/******/ })
/************************************************************************/
/******/ ([
/* 0 */
/***/ function(module, exports, __webpack_require__) {

	module.exports = __webpack_require__(1);


/***/ },
/* 1 */
/***/ function(module, exports, __webpack_require__) {

	/* REACT HOT LOADER */ if (false) { (function () { var ReactHotAPI = require("D:\\yuba_adm\\web\\node_modules\\react-hot-loader\\node_modules\\react-hot-api\\modules\\index.js"), RootInstanceProvider = require("D:\\yuba_adm\\web\\node_modules\\react-hot-loader\\RootInstanceProvider.js"), ReactMount = require("react/lib/ReactMount"), React = require("react"); module.makeHot = module.hot.data ? module.hot.data.makeHot : ReactHotAPI(function () { return RootInstanceProvider.getRootInstances(ReactMount); }, React); })(); } try { (function () {
	
	"use strict";
	
	var _a = __webpack_require__(2);
	
	var _a2 = _interopRequireDefault(_a);

	function _interopRequireDefault(obj) { return obj && obj.__esModule ? obj : { default: obj }; }

	/* REACT HOT LOADER */ }).call(this); } finally { if (false) { (function () { var foundReactClasses = module.hot.data && module.hot.data.foundReactClasses || false; if (module.exports && module.makeHot) { var makeExportsHot = require("D:\\yuba_adm\\web\\node_modules\\react-hot-loader\\makeExportsHot.js"); if (makeExportsHot(module, require("react"))) { foundReactClasses = true; } var shouldAcceptModule = true && foundReactClasses; if (shouldAcceptModule) { module.hot.accept(function (err) { if (err) { console.error("Cannot not apply hot update to " + "app.js" + ": " + err.message); } }); } } module.hot.dispose(function (data) { data.makeHot = module.makeHot; data.foundReactClasses = foundReactClasses; }); })(); } }

/***/ },
/* 2 */
/***/ function(module, exports, __webpack_require__) {

	/* REACT HOT LOADER */ if (false) { (function () { var ReactHotAPI = require("D:\\yuba_adm\\web\\node_modules\\react-hot-loader\\node_modules\\react-hot-api\\modules\\index.js"), RootInstanceProvider = require("D:\\yuba_adm\\web\\node_modules\\react-hot-loader\\RootInstanceProvider.js"), ReactMount = require("react/lib/ReactMount"), React = require("react"); module.makeHot = module.hot.data ? module.hot.data.makeHot : ReactHotAPI(function () { return RootInstanceProvider.getRootInstances(ReactMount); }, React); })(); } try { (function () {
	
	"use strict";
	
	Object.defineProperty(exports, "__esModule", {
	  value: true
	});
	
	var _b = __webpack_require__(3);
	
	var _b2 = _interopRequireDefault(_b);
	
	function _interopRequireDefault(obj) { return obj && obj.__esModule ? obj : { default: obj }; }
	
	console.info(_b2.default);
	exports.default = "a";
	
	/* REACT HOT LOADER */ }).call(this); } finally { if (false) { (function () { var foundReactClasses = module.hot.data && module.hot.data.foundReactClasses || false; if (module.exports && module.makeHot) { var makeExportsHot = require("D:\\yuba_adm\\web\\node_modules\\react-hot-loader\\makeExportsHot.js"); if (makeExportsHot(module, require("react"))) { foundReactClasses = true; } var shouldAcceptModule = true && foundReactClasses; if (shouldAcceptModule) { module.hot.accept(function (err) { if (err) { console.error("Cannot not apply hot update to " + "a.js" + ": " + err.message); } }); } } module.hot.dispose(function (data) { data.makeHot = module.makeHot; data.foundReactClasses = foundReactClasses; }); })(); } }

/***/ },
/* 3 */
/***/ function(module, exports, __webpack_require__) {

	/* REACT HOT LOADER */ if (false) { (function () { var ReactHotAPI = require("D:\\yuba_adm\\web\\node_modules\\react-hot-loader\\node_modules\\react-hot-api\\modules\\index.js"), RootInstanceProvider = require("D:\\yuba_adm\\web\\node_modules\\react-hot-loader\\RootInstanceProvider.js"), ReactMount = require("react/lib/ReactMount"), React = require("react"); module.makeHot = module.hot.data ? module.hot.data.makeHot : ReactHotAPI(function () { return RootInstanceProvider.getRootInstances(ReactMount); }, React); })(); } try { (function () {
	
	"use strict";
	
	Object.defineProperty(exports, "__esModule", {
	  value: true
	});
	
	var _a = __webpack_require__(2);
	
	var _a2 = _interopRequireDefault(_a);
	
	function _interopRequireDefault(obj) { return obj && obj.__esModule ? obj : { default: obj }; }
	
	console.info(_a2.default);
	exports.default = "b";
	
	/* REACT HOT LOADER */ }).call(this); } finally { if (false) { (function () { var foundReactClasses = module.hot.data && module.hot.data.foundReactClasses || false; if (module.exports && module.makeHot) { var makeExportsHot = require("D:\\yuba_adm\\web\\node_modules\\react-hot-loader\\makeExportsHot.js"); if (makeExportsHot(module, require("react"))) { foundReactClasses = true; } var shouldAcceptModule = true && foundReactClasses; if (shouldAcceptModule) { module.hot.accept(function (err) { if (err) { console.error("Cannot not apply hot update to " + "b.js" + ": " + err.message); } }); } } module.hot.dispose(function (data) { data.makeHot = module.makeHot; data.foundReactClasses = foundReactClasses; }); })(); } }

/***/ }
/******/ ]);
//# sourceMappingURL=test.js.map
```

## 整理后
```jsx 
(function(modules) {
	// 缓存
	var installedModules = {};
	//require方法实现
	function __webpack_require__(moduleId) {
		//在缓存中查找
		if(installedModules[moduleId])
			return installedModules[moduleId].exports;//负面作用：所有module相当于单例，修改其属性会造成全局影响
		var module = installedModules[moduleId] = {//初始化新module并缓存之
			exports: {},
			id: moduleId,//数组下标
			loaded: false
		};
		//module执行
		modules[moduleId].call(module.exports, module, module.exports, __webpack_require__);
		module.loaded = true;
		//导出exports
		return module.exports;
	}
	return __webpack_require__(0);//bootstrap
})
([
	function(module, exports, __webpack_require__) {//bootstrap，用于调用entry
		module.exports = __webpack_require__(1);
	},
	function(module, exports, __webpack_require__) {//app.js
		"use strict";
		var _a = __webpack_require__(2);
		var _a2 = _interopRequireDefault(_a);
		function _interopRequireDefault(obj)
		{ return obj && obj.__esModule ? obj : { default: obj }; }//ES6 import default支持
	},
	function(module, exports, __webpack_require__) {//a.js
		"use strict";

		Object.defineProperty(exports, "__esModule", {
		  value: true
		});

		var _b = __webpack_require__(3);
        
        //后期添加测试输出
        console.info(_b);//输出：Object {default: "b", __esModule: true}

		var _b2 = _interopRequireDefault(_b);

		function _interopRequireDefault(obj)
		{ return obj && obj.__esModule ? obj : { default: obj }; }//ES6 import default支持

		console.info(_b2.default);
		exports.default = "a";
	},
	function(module, exports, __webpack_require__) {//b.js
		"use strict";
		Object.defineProperty(exports, "__esModule", {
		  value: true
		});

		var _a = __webpack_require__(2);

		var _a2 = _interopRequireDefault(_a);

		function _interopRequireDefault(obj)
		{ return obj && obj.__esModule ? obj : { default: obj }; }//ES6 import default支持

		console.info(_a2.default);
		exports.default = "b";
        
        //后期添加测试输出
        console.info(module);//输出： Object {exports: { default:"b",__esModule:true}, id: 3, loaded: false}
	}
]);
```