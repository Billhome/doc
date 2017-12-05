##沉浸式体验  

在onCreate方法中加入如下代码可以取消掉状态栏;  

	View decorView = getWindow().getDecorView();
    int option = View.SYSTEM_UI_FLAG_FULLSCREEN;
    decorView.setSystemUiVisibility(option);  

去掉ActionBar:

	View decorView = getWindow().getDecorView();
    int option = View.SYSTEM_UI_FLAG_FULLSCREEN;
    decorView.setSystemUiVisibility(option);  

将状态栏设置为透明，并利用状态栏的空间（可以使用的版本号要搞清楚）：  

	if(Build.VERSION.SDK_INT >= Build.VERSION_CODES.LOLLIPOP){
            View decorView = getWindow().getDecorView();
            int option = View.SYSTEM_UI_FLAG_LAYOUT_FULLSCREEN
                    | View.SYSTEM_UI_FLAG_LAYOUT_STABLE;
            decorView.setSystemUiVisibility(option);
            getWindow().setStatusBarColor(Color.TRANSPARENT);
    }	

