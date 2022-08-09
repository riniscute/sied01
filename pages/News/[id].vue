<script setup lang="ts">
    /*********************************************************
    prog name: 最新消息明細頁, author: 勁陞, date: 2022/07/30
    Todo: 
    **********************************************************/	

    definePageMeta({
      title: 'SIED - ',
    })   	
</script>

<template>
<main>
  <div class="w-full h-10 mt-10 flex justify-center">
    <div class="bg-blue-300 w-[18rem] h-full rounded flex justify-evenly items-center">
      <a href="#" class="bg-blue-500 border-4 border-blue-300 rounded-lg h-full w-1/2 flex justify-center items-center text-lg font-semibold text-white">公告事項</a>
      <a href="#" class="h-full w-1/2 flex justify-center items-center text-lg font-semibold">最新活動</a>
    </div>
  </div>

  <div class="h-1 w-full mt-10 flex justify-center">
    <div class="bg-blue-300 w-4/5"></div>
  </div>

  <div class="w-full flex flex-col items-center">
    <div class="w-4/5 mt-5 flex flex-col">
      <a href="#" class="ml-4 mb-1 flex justify-left items-center text-xl font-semibold">
        2023 SIED將舉辦於2023/01/31～2023/0204
      </a>
      <div class="bg-blue-300 rounded-md h-10 w-[8rem] flex justify-center items-center text-lg">
        2022/05/21
      </div>
      <div class="ml-1 mt-10">
        經過輔導員的討論，最終決議將2023年SIED舉辦於1月31日至2月4日期間，活動報名時間將另行公布於此網站中，敬請多加關注。
      </div>
    </div>
  </div>
</main>	
</template>