```
<$set name="tv-freelinks" value={{$:/config/Freelinks/Enable}}>
```

* 上面的代码设置了一个 `tv-freelinks` 变量,  这是一个全局变量, 可以在widget 里面通过this.getVariable('tv-freelinks') 获得

具体见 [[FreeLinks|$:/plugins/tiddlywiki/freelinks]]