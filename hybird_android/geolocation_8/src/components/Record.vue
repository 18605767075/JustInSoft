<template>
	<div class="record">
		<div class="record-title">Click following button to record voice:</div>
		<input @click="startRecord" type="button" value="录音">
		<input @click="stopRecord" type="button" value="停止">
	</div>
</template>

<script>
	import Record from "../commons/record-sdk";
	export default {
		name: "Record",
		data() {
			return {
				recorder: new Record()
			};
		},
		methods: {
			startRecord: function() {
				console.log("start to record now.");
				let self = this;
				self.recorder.startRecord({
					success: res => {
						console.log("start record successfully.");
					},
					error: res => {
						console.log("start record failed.");
					}
				});
			},
			stopRecord: function() {
				console.log("stop record now.");
				let self = this;
				self.recorder.stopRecord({
					success: res => {
						console.log("stop record successfully.");
					},
					error: res => {
						console.log("stop record failed.");
					}
				});
			}
		}
	};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
	.record {
		width: 100%;
		height: 100px;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-wrap: wrap;
		font-weight: bold;
	}

	.record-title {
		width: 100%;
	}

	#input {
		width: 50px;
		height: 20px;
		/* margin-left: 10%; */
	}

	.record-play {
		width: 100%;
		height: 100px;
	}
</style>
