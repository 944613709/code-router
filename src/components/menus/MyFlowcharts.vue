<template>
  <div id="container"></div>
</template>
<script>
import { Graph } from "@antv/x6";
export default {
    data(){
        return{
            graph: null
        }
    },
  name: "MyGraph",
  mounted() {
      this.initGraph();
  },
  methods: {
      initGraph() {
          // 1. 节点 nodes 和边 edges 字段 的 JSON 数据
          const data = {
              // 节点
              nodes: [
                  {
                      id: "node1", // String，可选，节点的唯一标识
                      x: 40, // Number，必选，节点位置的 x 值
                      y: 180, // Number，必选，节点位置的 y 值
                      width: 80, // Number，可选，节点大小的 width 值
                      height: 40, // Number，可选，节点大小的 height 值
                      label: "node1" // String，节点标签
                  },
                  {
                      id: "node2", // String，节点的唯一标识
                      x: 160, // Number，必选，节点位置的 x 值
                      y: 180, // Number，必选，节点位置的 y 值
                      width: 80, // Number，可选，节点大小的 width 值
                      height: 40, // Number，可选，节点大小的 height 值
                      label: "node2" // String，节点标签
                  },
                  {
                      id: "node3", // String，可选，节点的唯一标识
                      x: 320, // Number，必选，节点位置的 x 值
                      y: 100, // Number，必选，节点位置的 y 值
                      width: 80, // Number，可选，节点大小的 width 值
                      height: 40, // Number，可选，节点大小的 height 值
                      label: "node3" // String，节点标签
                  },
                  {
                      id: "node4", // String，可选，节点的唯一标识
                      x: 320, // Number，必选，节点位置的 x 值
                      y: 300, // Number，必选，节点位置的 y 值
                      width: 80, // Number，可选，节点大小的 width 值
                      height: 40, // Number，可选，节点大小的 height 值
                      label: "node4" // String，节点标签
                  },
              ],
              // 边
              edges: [
                  {
                      source: "node1", // String，必须，起始节点 id
                      target: "node2" // String，必须，目标节点 id
                  },
                  {
                      source: "node2", // String，必须，起始节点 id
                      target: "node3" // String，必须，目标节点 id
                  },
                  {
                      source: "node2", // String，必须，起始节点 id
                      target: "node4" // String，必须，目标节点 id
                  },
              ]
          };

          // 2. 渲染画布
          this.graph = new Graph({
          panning: false,
          container: document.getElementById('container'),
          width: 800,
          height: 600,
        //   background: {
        //     color: '#fffbe6', // 设置画布背景颜色
        //   },
        //   grid: {
        //     size: 10,      // 网格大小 10px
        //     visible: true, // 渲染网格背景
        //   },
        });

          // 3. 渲染我们的节点和边
          this.graph.fromJSON(data);
      }
  }
};
</script>
