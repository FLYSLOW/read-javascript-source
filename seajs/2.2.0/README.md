# Note
## Variable in closure
	seajs
	  +- version
	  +- data                // {Object}
	       +- events // {Object}
	  +- cache // {Object}
	  +- on // {Function} 添加事件
	  +- off // {Function} 移除事件
	  +- emit // {Function} 触发事件
	  +- resolve // {Fuction} id2Uri
	  +- request // 请求assets并添加到dom树
	data = seajs.data
	
	// RegExp
	DIRNAME_RE // {RegExp} for dirname
	DOT_RE // {RegExp} for realpath
	DOUBLE_DOT_RE // {RegExp} for realpath
	DOUBLE_SLASH_RE // {RegExp} for realpath
	PATHS_RE // {RegExp} for parsePaths
	VARS_RE // {RegExp} for parseVars
	ABSOLUTE_RE // {RegExp} for addBase
	ROOT_DIR_RE // {RegExp} for addBase
	IS_CSS_RE // 测试url是否为css url
	REQUIRE_RE // 匹配require
	SLASH_RE // 匹配\\
	
	// util
	isType                   // {Function}
	isObject // {Function}
	isString // {Function}
	isArray // {Function}
	isFunction // {Function}
	dirname // {Function} 获取路径的目录名
	realpath // {Function} 相对路径 => 绝对路径
	normalize // {Function} 移除尾部的`#`,尝试添加`.js`后缀
	parseAlias // {Function} 解析seajs.data.alias
	parsePaths // {Function} 解析seajs.data.paths
	parseVars // {Function} 解析seajs.data.vars
	parseMap // {Function} 解析seajs.data.map
	addBase // {Function} 尝试 id => 绝对路径
	id2Uri // {Function}
	cid // {Function} count id generater for _cid
	emit = seajs.emit
	request = seajs.request
	addOnload // 添加onload回调
	pollCss // 对于isOldWebKit，轮询确定css是否已经加载完毕，手动触发callback。
	getCurrentScript // 获取当前的script节点，used by Module.define
	parseDependencies // 根据代码中的require解析模块依赖
	
	getScriptAbsoluteSrc // {Function}
	
	// cache
	doc // {HTMLElement} document
	head // {HTMLElement} head node
	baseElement // base node
	scripts // {HTMLElements} document.scripts
	loaderScript // seajs node
	currentlyAddingScript
	interactiveScript
	isOldWebKit
	
	cwd // {String} current working directory
	loaderDir // {String} seajs 所在目录
	_cid // {Number} count id 缓存，从0开始
	cachedMods = seajs.cache
	anonymousMeta // 匿名模块元数据
	fetchingList // {Object}
	fetchedList // {Object}
	callbackList // {Object}
	STATUS = Module.STATUS // {Object} FETCHING, SAVED, LOADING, LOADED, EXECUTING, EXECUTED
	
	// module constructor
	Module
	

## Parse id to uri（also `seajs.resolve`）
1. Parse alias
2. Parse paths
3. Parse vars
4. Normalize, 移除尾部的`#`,尝试添加`.js`后缀
5. Add base
6. Parse map, like redirect