<template>
    <div>

    </div>
</template>
<script>
export default {
    data(){
        return {
            async function () {
  let allData = [];
  let morePagesAvailable = true;
  let currentPage = 0;

  while(morePagesAvailable) {
    currentPage++;
    const response = await fetch(`https://api.github.com/repos/axios/axios/issues?per_page=100`)
    let { data, total_pages } = await response.json();
    data.forEach(e => allData.unshift(e));
    morePagesAvailable = currentPage < total_pages;
  }

  return allData;
}
        }
    }
}

</script>