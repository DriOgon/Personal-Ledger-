<template>
	 <view>
	        <ui-echarts ref="chart" :option="option" exportBase64></ui-echarts>
	        <image v-if="image" :src="image"></image>
	        <button type="primary" size="mini" @click="toImage">导出图片</button>
	    </view>
</template>

<script>
	export default {
	    data () {
	        return {
	            image: null,
	            option: {}
	        }
	    },
	    onReady() {
	        this.option = {
	            grid: {
	                right: 20
	            },
	            xAxis: {
	                type: 'category',
	                data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
	            },
	            yAxis: {
	                type: 'value'
	            },
	            series: [{
	                data: [150, 230, 224, 218, 135, 147, 260],
	                type: 'line'
	            }]
	        }
	    },
	    methods: {
	        toImage () {
	            this.$refs?.chart.toImageFile({
	                /**
	                 * tempFilePath 图片路径, H5导出也是base64
	                 * base64 图片base64
	                 */
	                success: ({ tempFilePath, base64 }) => {
	                    this.image = base64;
	                }
	            })
	        }
	    }
	}
</script>

<style>
</style>