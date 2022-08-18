<script setup lang="ts">
    /*********************************************************
    prog name: 常見Q&A, author: 季芸, date: 2022/07/30
    Todo: 
    **********************************************************/	
    import { ref, onMounted } from "vue"
    import jsonData from "../static/qna.json"

    const isShow = ref(false)
    const iValue = ref(-1)
    const liwaData = ref([])

    const toggleShow = (idx) => {
    	iValue.value = idx
    	console.log('isShow1 =', liwaData.value[idx].isShow)
    	liwaData.value[idx].isShow = !liwaData.value[idx].isShow
    	console.log('isShow2 =', liwaData.value[idx].isShow, ';index =', idx)
    	console.log('liwaData =', liwaData.value)
    }

    const setShow = () => {
    	console.log('debug')
    }

    onMounted(() => {
        liwaData.value = jsonData
        // console.log('liwaData =', liwaData.value)
    })


    definePageMeta({
      title: '常見Q&A ',
    })       	
</script>

<template>
<div class="w-full h-[800px] lg:w-[1024px] lg:mx-auto">
    <div class="w-full h-[80vh]">
        <!-- 網頁內容由此開始 -->
		<div v-if="liwaData.length" class="w-full mt-5 bg-gradient-to-r from-emerald-100 via-cyan-200 to-sky-400 relative">
			<div
				v-for="(ques,index) in liwaData"
				:key="index"
				class="flex flex-col"
			>
				<div class="w-full flex flex-row">
					<div class="w-[calc(100%_-_2rem)] text-2xl font-semibold text-black-500 mt-5 ml-3">{{ ques.question }}
					</div>
					<div class="w-8 pt-2" @click="toggleShow(index)">
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
				</div>					
			</div>
		</div>
	</div>
</div>
</template>