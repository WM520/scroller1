<template>
	<div>
			<ul>
		<li v-for="item in list">
			<p>111111111</p>
		</li>
	</ul>
	<!-- 滑动加载更多组件 -->
	<infinite-scroll :scroller="scroller" :loading="loading" @load="loadMore"/>
	</div>

</template>

<script>
export default {
  data() {
    return {
      refreshing: false,
      loading: false,
      scroller: null,
      list: [ {}, {}, {}, {}, {}, {}, {}, {}, {},{}, {}, {}, {}, {}, {}, {}, {}, {},{}, {}, {}, {}, {}, {}, {}, {}, {},{}, {}, {}, {}, {}, {}, {}, {}, {}]
    }
  },
  mounted() {
  	this.scroller = this.$el;
  },
  methods: {
  	loadMore() {
			let vue = this;
			this.loading = true;
			console.log('11111111');
			setTimeout(() => {
				vue.getList();
			}, 500)
	},
	getList() {
		for (let i = 0; i < 10; i++) {
			var item = i;
			this.list.push(item);
			this.loading = false;
		};
	}
  }
}
</script>

<style lang="css">

</style>
