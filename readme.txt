中坐标绘制曲线上采用了口碑较好的开源框架MPAndroidChart，该框架非常好用且稳定，以下对它的一些说明：

API
这个项目的具体的API调用，可参考文档
https://jitpack.io/com/github/PhilJay/MPAndroidChart/v3.0.0-beta1/javadoc/

我还找到一个简洁版的（不过是繁体字）
https://github.com/25sprout/ChartLib-Demo-Android#ValueFormatter


相关文章仅供参考，网上还有很多
http://blog.csdn.net/u013338165/article/details/44810025

1、直接使用jar方式，需要导入mpchartlib.jar，nineoldandroidsjar。
2、使用libproject的方式，作为项目依赖。
步骤:
如果使用 LineChart, BarChart, ScatterChart, CandleStickChart or PieChart
, 可以直接在xml中定义。
<com.github.mikephil.charting.charts.LineChart
        android:id="@+id/chart"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />
LineChart chart = (LineChart) findViewById(R.id.chart);
或则直接在代码中声明和实例化。
LineChart chart = new LineChart(Context);
主要的Api方法:
setDescription(String desc) : 设置表格的描述
setDescriptionTypeface(Typeface t) :自定义表格中显示的字体
setDrawYValues(boolean enabled) : 设置是否显示y轴的值的数据
setValuePaintColor(int color) :设置表格中y轴的值的颜色，但是必须设置setDrawYValues（true）
setValueTypeface(Typeface t):设置字体
setValueFormatter(DecimalFormat format) : 设置显示的格式
setPaint(Paint p, int which) : 自定义笔刷
public ChartData getDataCurrent() :返回ChartData对象当前显示的图表。它包含了所有信息的显示值最小和最大值等
public float getYChartMin() : 返回当前最小值
public float getYChartMax() : 返回当前最大值
public float getAverage() : 返回所有值的平均值。
public float getAverage(int type) : 返回平均值
public PointF getCenter() : 返回中间点
public Paint getPaint(int which) : 得到笔刷
setTouchEnabled(boolean enabled) : 设置是否可以触摸，如为false，则不能拖动，缩放等
setDragScaleEnabled(boolean enabled) : 设置是否可以拖拽，缩放
setOnChartValueSelectedListener(OnChartValueSelectedListener l) : 设置表格上的点，被点击的时候，的回调函数
setHighlightEnabled(boolean enabled) : 设置点击value的时候，是否高亮显示
public void highlightValues(Highlight[] highs) : 设置高亮显示
saveToGallery(String title) : 保存图表到图库中
saveToPath(String title, String pathOnSD) : 保存.
setScaleMinima(float x, float y) : 设置最小的缩放
centerViewPort(int xIndex, float val) : 设置视口
fitScreen() : 适应屏幕
动画:
所有的图表类型都支持下面三种动画，分别是x方向，y方向，xy方向。
animateX(int durationMillis) : x轴方向
animateY(int durationMillis) : y轴方向
animateXY(int xDuration, int yDuration) : xy轴方向
mChart.animateX(3000f); // animate horizontal 3000 milliseconds
// or:
mChart.animateY(3000f); // animate vertical 3000 milliseconds
// or:
mChart.animateXY(3000f, 3000f); // animate horizontal and vertical 3000 milliseconds