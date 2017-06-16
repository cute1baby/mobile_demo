###display
老版本
    display:box;  //不生效
    display:-webkit-box;
新版本
    display:flex

在移动端，-webkit-box比flex兼容性高,好多安卓只兼容-webkit-box
###控制容器的布局方向
    老版本
        -webkit-box-orient:horizontal;  //水平
        -webkit-box-orient:vertical;   //垂直
    新版本
        flex-direction:row;  //水平
        flex-direction:column;  //垂直

###项目的排列方向
老版本
    -webkit-box-direction:normal;  //正常顺序
    -webkit-box-direction:normal;  //倒叙      
新版本
    flex-direction:row-reverse; 水平倒叙(但是与老版本位置不一样)
    flex-direction:column-reverse; 垂直倒叙(但是与老版本位置不一样)

###富裕空间的管理(不会给项目分配空间，只是确定富裕空间的位置)
把老版本模拟出新版本的样式
    水平：
        -webkit-box-pack:start;  把富裕空间放在右边管理
        -webkit-box-pack:end;  把富裕空间放在左边管理
        -webkit-box-pack:center;把富裕空间放在左右两边管理
        -webkit-box-pack:justify; 把富裕空间放在每两个项目中间管理
    垂直：
        -webkit-box-align:start;  把富裕空间放在下边管理
        -webkit-box-align:end;    把富裕空间放在下边管理
        -webkit-box-align:center; 把富裕空间放在上下边管理
                        stretch  项目没有高度的时候，默认把项目的高度撑开



新版本   
    flex-direction:row-reverse;
    没有reverse:start
    有reverse:end

    flex-direction自带三个功能：容器的布局方向
                                项目的排列方向
                                自带富裕空间管理

但是新版本有自己的富裕空间管理
    水平:
        justify-content:flex-start;    右
                        flex-end;      左
                        center;        两边
                        space-between; 每两个项目之间
                        space-around;   在项目两侧    


    垂直:
        align-items:flex-start;
                    flex-end;
                    center;
                    baseline;
                    stretch;

###弹性空间管理(项目)
    会给各个项目分配空间
    老版本
        -webkit-box-flex:1;   项目被均等分开
        将富裕空间分配给各个项目
        问题：如果给其中一个项目指定一个宽度，那最后在此宽度的基础上增加富裕宽度

    新版本
        flex-grow:1;(与老版本效果一样,给其中一个项目指定一个宽度，那最后在此宽度的基础上增加富裕宽度)
        或者flex:1;(但是，给其中一个项目指定一个宽度,没有任何影响)

