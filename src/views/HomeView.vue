<template>
  <div class="home">
    <nav class="border fixed split-nav">
      <div class="nav-brand">
        <h3><a href="https://www.xchao.work" target="_blank">Get Palpitate</a></h3>
      </div>
      <div class="collapsible">
        <input id="collapsible1" type="checkbox" name="collapsible1">
        <label for="collapsible1">
          <div class="bar1"></div>
          <div class="bar2"></div>
          <div class="bar3"></div>
        </label>
        <div class="collapsible-body">
          <ul class="inline">
            <li><a href="https://github.com/Web-Zombies" target="_blank">Github</a></li>
            <li><a href="https://xchao.work/about" target="_blank">About</a></li>
            <li><a href="javascript:void(0);" @click="leaveRow">离开</a></li>
          </ul>
        </div>
      </div>
    </nav>
    <div class="row site box-top" id="top">
      <div class="sm-12 md-8 col">
        <div class="paper">
          <!-- <h3 class="sidebar-title " style="text-align:center">
            Look at me
          </h3> -->
          <div class="row">
            <iframe :src="iframeUrl" frameborder="0" style="scrolling:no" width="100%" height="670px"></iframe>
          </div>
        </div>
      </div>
      <div class="sm-12 md-4 col sidebar">
        <div class="paper">
          <h3 class="sidebar-title " style="text-align:center">
            展示列表
          </h3>
          <div class="row">
            <div class="collapsible" style="width: 100%;" v-for="(item,index) in collecList" :key="index" @click="collecRow(item.url)">
              <label for="collapsible11">{{item.name}} <span v-if="item.url == iframeUrl">👈</span></label>
            </div>
          </div>
        </div>
        <div class="paper">
          <div class="">
            <fieldset class="form-group row flex-center">
              <label for="paperSwitch1" class="paper-switch-tile">
                <input id="paperSwitch1" name="paperSwitch1" type="checkbox" />
                <div class="paper-switch-tile-card border">
                  <div class="paper-switch-tile-card-front border">🎈</div>
                  <div class="paper-switch-tile-card-back border background-secondary">I'm a</div>
                </div>
              </label>
              <label for="paperSwitch2" class="paper-switch-tile">
                <input id="paperSwitch2" name="paperSwitch2" type="checkbox" />
                <div class="paper-switch-tile-card border">
                  <div class="paper-switch-tile-card-front border background-warning">✨</div>
                  <div class="paper-switch-tile-card-back border background-success">zombies</div>
                </div>
              </label>
            </fieldset>
          </div>
          <div class="row flex-spaces">
            <textarea class="col-8 col" id="large-input" placeholder="源码以上传至github"></textarea>
            <button class="col-3 col">发射~</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { useRouter } from "vue-router";
import { reactive, ref } from "vue";
export default ({
  setup () {
    const router = useRouter();
    let collecList = reactive([
      { name: 'Echarts-ChinaMap', url: 'http://pro.xchao.work/Echarts-ChinaMap/' },
      { name: 'Three-Model', url: 'http://pro.xchao.work/Three-Model/' },
    ]);
    let iframeUrl = ref(collecList[1].url);
    function leaveRow () { //离开
      router.push({ path: '/' })
    }
    function collecRow (url) {//项目集点击
      iframeUrl.value = url; //注意修改ref定义的值需要.value
    }
    return {
      collecList, iframeUrl,
      collecRow,
      leaveRow
    };
  },
})
</script>
<style lang="scss" scoped>
.box-topP {
  position: relative;
}
.box-top {
  margin-top: 60px;
}
</style>