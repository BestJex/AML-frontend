<template>
	<el-form ref="form" :model="form" label-width="80px" @submit.prevent="onSubmit" style="margin:20px;width:60%;min-width:600px;">
		<el-form-item label="任务名称">
			<el-input v-model="form.name"></el-input>
		</el-form-item>
		<el-form-item label="模型类型">
			<el-select v-model="form.region" placeholder="请选择模型类型">
				<el-option label="分类" value="classfication"></el-option>
				<el-option label="回归" value="regression"></el-option>
				<el-option label="聚类" value="cluster"></el-option>
			</el-select>
		</el-form-item>
<!--		<el-form-item label="活动时间">-->
<!--			<el-col :span="11">-->
<!--				<el-date-picker type="date" placeholder="选择日期" v-model="form.date1" style="width: 100%;"></el-date-picker>-->
<!--			</el-col>-->
<!--			<el-col class="line" :span="2">-</el-col>-->
<!--			<el-col :span="11">-->
<!--				<el-time-picker type="fixed-time" placeholder="选择时间" v-model="form.date2" style="width: 100%;"></el-time-picker>-->
<!--			</el-col>-->
<!--		</el-form-item>-->
<!--		<el-form-item label="即时配送">-->
<!--			<el-switch on-text="" off-text="" v-model="form.delivery"></el-switch>-->
<!--		</el-form-item>-->
		<el-form-item label="模型选择">
			<el-checkbox-group v-model="form.type">
				<el-checkbox label="朴素贝叶斯" name="type"></el-checkbox>
				<el-checkbox label="决策树" name="type"></el-checkbox>
				<el-checkbox label="支持向量机" name="type"></el-checkbox>
				<el-checkbox label="神经网络" name="type"></el-checkbox>
				<el-checkbox label="线性回归" name="type"></el-checkbox>
				<el-checkbox label="逻辑回归" name="type"></el-checkbox>
				<el-checkbox label="K-means" name="type"></el-checkbox>
			</el-checkbox-group>
		</el-form-item>
		<el-form-item label="模型选择">
			<el-checkbox-group v-model="form.type">
				<el-checkbox label="ROC曲线" name="type"></el-checkbox>
				<el-checkbox label="混淆矩阵" name="type"></el-checkbox>
				<el-checkbox label="均方误差" name="type"></el-checkbox>


			</el-checkbox-group>
		</el-form-item>
		<el-form-item label="参数搜索">
			<el-input type="textarea" v-model="form.desc"></el-input>
		</el-form-item>
		<el-form-item>
			<el-button type="primary">立即创建</el-button>
			<el-button @click.native.prevent>取消</el-button>
		</el-form-item>
	</el-form>
</template>

<script>
	export default {
		data() {
			return {
				form: {
					name: '',
					region: '',
					date1: '',
					date2: '',
					delivery: false,
					type: [],
					resource: '',
					desc: ''
				}
			}
		},
		methods: {
			onSubmit() {
				console.log('submit!');
			}
		}
	}

</script>