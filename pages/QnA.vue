<script setup lang="ts">
    /*********************************************************
    prog name: 常見Q&A, author: 季芸, date: 2022/07/30
    Todo: 
    **********************************************************/	
    import { ref, onMounted } from "vue"
    import liwaData from "../static/qna.json"

    const isShow = ref(false)

    const toggleShow = () => {
    	isShow.value = !isShow.value
    }

    onMounted(() => {

    })


    definePageMeta({
      title: '常見Q&A ',
    })       	
</script>

<template>
<div class="w-full h-[800px] lg:w-[1024px] lg:mx-auto">
    <div class="w-full h-[80vh]">
        <!-- 網頁內容由此開始 -->
		<div v-if="liwaData.length" class="w-full h-20 mt-5 bg-gradient-to-r from-emerald-100 via-cyan-200 to-sky-400 relative">
			<div
				class="relative" 
				v-for="(ques, index) in liwaData"
				:key="index"
			>
				<div class="w-full flex flex-row">
					<div class="w-[calc(100%_-_2rem)] text-2xl font-semibold text-black-500 mt-5 ml-3">{{ ques.question }}
					</div>
					<div class="w-8 pt-2" @click="toggleShow">
						<svg xmlns="http://www.w3.org/2000/svg" class="h-7 w-7" fill="#fee" viewBox="-1 -1 24 24" stroke="currentColor">
							<path stroke-linecap="round" stroke="#f33" stroke-linejoin="round" stroke-width="6" d="M12 4v16m8-8H4" />
						</svg>
					</div>					
				</div>
				<div 
					v-if="ques.isShow" 
					class="w-full h-[12rem] bg-cyan-100"
				>
					<div class="text-2xl font-semibold mt-5 ml-3">{{ ques.answer }}</div>
<!-- 							<div class="text-2xl font-semibold mt-5 ml-3">A1:</div> -->				
				</div>
			</div>
<!-- 			<div class="relative">  
				<p class="float-left text-2xl font-semibold text-black-500 mt-5 ml-3">Q1: 如何報名?</p> 
				<div class="absolute top-6 right-4" @click="toggleShow">
					<svg xmlns="http://www.w3.org/2000/svg" class="h-7 w-7" fill="#fee" viewBox="-1 -1 24 24" stroke="currentColor">
						<path stroke-linecap="round" stroke="#f33" stroke-linejoin="round" stroke-width="6" d="M12 4v16m8-8H4" />
					</svg>
				</div>
			</div> -->
<!-- 			<div 
				v-if="isShow"
				class="w-full h-[12rem] bg-cyan-100 absolute top-20"
			>
			    <div class="flow-root flex flex-col">  
					<p class="float-left font-semibold text-black-500 mt-5 ml-3"> 	
						<div class="text-2xl font-semibold mt-5 ml-3">A1:</div>
						<div class="ml-3">可以進入SIED的Instagram、FB以及官網上皆會定期更新並公布報名日期同時張貼報名表單網址，再請各位進入表單填寫資料即可。</div>
					</p> 
				</div>
			</div> -->
		</div>
<!-- 		<div class="w-full h-20 mt-5 bg-gradient-to-r from-emerald-100 via-cyan-200 to-sky-400" >
			<div class="flow-root">  
				<p class="float-left text-2xl font-semibold text-black-500 mt-5 ml-3">Q2: 如何知道自己已經通過審核/沒收到通知信?</p> 
				<p class="float-right">
					<img src="https://img.onl/DgzxFj" class="max-w-none ml-3 mt-4 mr-3" width="50" />
				</p>
			</div>
			<div class="w-full h-[12rem] mt-7 bg-cyan-100">
			    <div class="flow-root flex flex-col">  
					<p class="float-left font-semibold text-black-500 mt-5 ml-3"> 	
						<div class="text-2xl font-semibold mt-5 ml-3">A2:</div>
						<div class="ml-3"> SIED課程組這邊會在全部資料審核完畢後寄發email通知，再請各位到信箱查看是否有收到相關信息。
							若是沒有收到通知郵件再麻煩各位學員到信箱內的垃圾桶查看或私訊官網將有專人為您服務。
						</div>
					</p> 
					<p class="float-right">
						<img src="https://img.onl/3E09Oc" class="max-w-none ml-3 mt-4 mr-3" width="50" />
					</p>
				</div>
			</div>
		</div> -->
	</div>
</div>
</template>