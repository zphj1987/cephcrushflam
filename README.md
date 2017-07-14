# cephcrushflam
get osd crush flame

##项目来源
性能优化大神Brendan Gregg发明了火焰图来定位性能问题，通过图表就可以发现问题出在哪里，通过svg矢量图来查看性能卡在哪个点，哪个操作占用的资源最多

在查看了原始数据后，这个分析的原理是按层级来对调用进行一个统计的计数，然后以层级去做比对，来看横向的占用的比例情况

基于这个原理，把osd tree的数据和pg数据可以做一个层级的组合，从而可以很方便的看出pg的分布情况，主机的分布情况，还可以进行搜索，在一个简单的图表内汇聚了大量的信息

##使用方法

wget -o /sbin/stackcollapse-crush 
wget -o /sbin/flamegraph

 /sbin/stackcollapse-crush > /tmp/mydata
/sbin/flamegraph /tmp/mydata > /tmp/mycrush.svg

##效果图



##