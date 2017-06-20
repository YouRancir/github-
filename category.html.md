<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>河北中学</title>
<link href="{CSS_PATH}hezhong/css/news.css" rel="stylesheet" type="text/css" />

</head>

<body>
	<div id="mybody">
    	<div id="top">
        	<div class="menu">
            {template "content","nav"}
            </div>
        </div>
      <div id="dh">
            	<h1><a href="index.html"> - {catpos($catid," - ")}</h1>
            	<div id="search">
            <input name="search" type="text" class="search_text" /><input name="searchbut" type="button" class="search_but" value=" " />
            </div>
          </div>
        <div id="left">
        	<div id="leftmenu">
            	<h1>{$CATEGORYS[$catid]['catname']}</h1>
                <ul>
                  {pc:content action="category" catid="$catid"}
                      {loop $data $val}
                      <a href="{$val['url']}">{$val['catname']}</a>
                      {/loop}
                  {/pc}
              </ul>
            </div>
          <div id="pic">
            {template "content","pic"}
          </div>

            </div>
        </div>

        <div id="right">
        	<h1>{$CATEGORYS[$catid]['catname']}</h1>
            <ul>
                <!-- {pc:content action="lists" catid="$catid" num="1" page="pages"} -->
                {pc:content order='inputtime DESC' catid="$catid" action="categorys" num="10" page="$page"}
                    {loop $data $val}
                        <li>
                          <a href="{$val['url']}">{str_cut($val['title'],70)}</a>
                          <span class="newsdate">{date('Y-m-d',$val['inputtime'])}</span>
                        </li>
                  {/loop}
                {/pc}
            </ul>
            <div id="page">{$pages}</div>
        </div>

      </div>

	<div id="foot">
 		Copyright © 2008－2013 http://www.***.com All Rights Reserved   网站备案：冀ICP备00000000号
	</div>
</body>
<script type="text/javascript" src="js/pic.js"></script>
</html>
