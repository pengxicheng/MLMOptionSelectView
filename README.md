# MLMOptionSelectView

#弹出-选择-展示框
可设置弹出的方向，是否有箭头，是否可以编辑删除。

#效果图展示
![image](https://github.com/MengLiMing/MLMOptionSelectView/blob/master/pointShow.gif)
![image](https://github.com/MengLiMing/MLMOptionSelectView/blob/master/viewShow.gif)

###更新 - 添加新方法，从点击点展开视图,具体使用参考Demo
```objc
/**
 *  弹出视图
 *
 *  @param tapPoint      点击的点
 *  @param width         能够显示的最大宽度
 *  @param directionType 弹出方向，在上下或者左右都能显示时，优先选择
 */
- (void)showTapPoint:(CGPoint)tapPoint
           viewWidth:(CGFloat)width
           direction:(MLMOptionSelectViewDirection)directionType;
```
#属性介绍
###需要设置的属性

    //设置返回的cell，用于自定义返回的下拉框中的cell样式
    @property (nonatomic, copy) UITableViewCell*(^cell)(NSIndexPath *);
    //返回的行数
    @property (nonatomic, copy) NSInteger(^rowNumber)() ;
    //设置返回的每一行的高度
    @property (nonatomic, copy) float(^optionCellHeight)();
    //点击的回调
    @property (nonatomic, copy) ActionBack selectedOption;
    //在设置可以编辑之后，可在其中自己写删除事件
    @property (nonatomic, copy) ActionBack removeOption;

###调节样式的属性
   
    //设置显示的最大行数
    @property (nonatomic, assign) NSInteger maxLine;
    //设置是否可以进行编辑
    @property (nonatomic, assign) BOOL canEdit;
    //设置是否含有箭头
    @property (nonatomic, assign) MLMOptionSelectViewType optionType;
    //设置展开时的动画样式，是缩放还是竖直水平展开，缩放 NO 竖直或水平展开 YES
    @property (nonatomic, assign) BOOL vhShow;
    //改变值，如果是缩放动画时，可以改变动画开始的点
    @property (nonatomic, assign) CGFloat arrow_offset;//(0 - 1之间)
    ///选择样式，是否开启多选,默认NO
    @property (nonatomic, assign) BOOL multiSelect;
    
    
###弹出视图方法
 
     //viewPoint       弹出视图之后视图的origin，请根据你显示的方向，填写正确的点
     //width           视图的宽，在无法完全展示时会有所改变
     //target          如果你的弹出view需要在某个view的周围显示，不要犹豫就填它
     //directionType   展示的方向，在左右或者上下都能显示的情况下，优先选择的方向
     - (void)showViewFromPoint:(CGPoint)viewPoint
                     viewWidth:(CGFloat)width
                    targetView:(UIView *)targetView
                     direction:(MLMOptionSelectViewDirection)directionType;
 
    
