<template>
  <div class="pt-10 flex flex-row">
    <div class="snippet-holder rounded-md shadow-lg font-Roboto" v-for="jsondata in snippet" :key="jsondata.id">
      <div class="snippet-image relative">
        <img src="http://placeimg.com/400/300/arch" />
        <span class="material-icons-outlined absolute hearticon">
favorite_border
</span>
      </div>
      <div class="snippet-details text-left">
        <div class="snippet-highlight py-5 pl-5">
          <span class="snippet-type md:uppercase font-semibold text-base">{{ jsondata.snippettype }} . </span>
          <span class="snippet-time md:uppercase font-semibold text-base">{{ jsondata.snippetage }} Old</span>
          <div class="snipppet-price text-4xl font-semibold my-1">${{ jsondata.snippetprice }}</div>
          <div class="snippet-add text-sm py-1">
            {{ jsondata.snippetaddress }}, {{ jsondata.snippetcity }}, {{ jsondata.snippetcounty }}, {{ jsondata.snippetzipcode }}
          </div>
        </div>
        <div class="snippet-features py-5 pl-5">
          <ul>
            <li class="mr-20 ml-0"><span class="material-icons text-3xl">bed</span> <span class="text-base"> <span class="font-semibold">{{ jsondata.bedrooms }} </span> Bedroom</span> </li>
            <li><span class="material-icons-outlined text-3xl">shower</span> <span class="text-base"><span class="font-semibold">{{ jsondata.bathrooms }} </span> Bathroom</span> </li>
          </ul>
        </div>
        <div class="snippet-owner py-5 pl-5">
          <h4 class="md:uppercase font-bold text-sm mb-3">Realtor</h4>
          <div class="inline-block align-middle"><img src="http://placeimg.com/80/80/people" width="60" class="rounded-full float-left" />
            </div>
          <div class="ml-5 inline-block align-middle">
            <span class="block font-bold text-base">{{ jsondata.realtorname }}</span>
            <span class="block font-bold text-sm ">{{ jsondata.realtorcontect }}</span>
            <span>Error</span>
          </div>
          <div class="clear-both"></div>
        </div>
      </div>
    </div>



     <div class="snippet-holder rounded-md shadow-lg font-Roboto">
      <div class="snippet-image relative">
        <img src="http://placeimg.com/640/480/arch" />
        <span class="material-icons-outlined absolute hearticon">
favorite_border
</span>
      </div>
      <div class="snippet-details text-left">
        <div class="snippet-highlight py-5 pl-5">
          <span class="snippet-type md:uppercase font-semibold text-base">Detached House . </span>
          <span class="snippet-time md:uppercase font-semibold text-base">5y Old</span>
          <div class="snipppet-price text-4xl font-semibold my-1">$350,000</div>
          <div class="snippet-add text-sm py-1">
            1655 Fulton Street, Parkersburg, WV 26003
          </div>
        </div>
        <div class="snippet-features py-5 pl-5">
          <ul>
            <li class="mr-20 ml-0"><span class="material-icons text-3xl">bed</span> <span class="text-base"> <span class="font-semibold">3 </span> Bedroom</span> </li>
            <li><span class="material-icons-outlined text-3xl">shower</span> <span class="text-base"><span class="font-semibold">2 </span> Bathroom</span> </li>
          </ul>
        </div>
        <div class="snippet-owner py-5 pl-5">
          <h4 class="md:uppercase font-bold text-sm mb-3">Realtor</h4>
          <div class="inline-block align-middle"><img src="http://placeimg.com/60/60/people" class="rounded-full float-left" />
            </div>
          <div class="ml-5 inline-block align-middle">
            <span class="block font-bold text-base">Gary M. Abbott</span>
            <span class="block font-bold text-sm ">304-482-3995</span>
          </div>
          <div class="clear-both"></div>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: "BankGreen",
  data(){
    return{
      snippet:[]
    }
  },
  mounted(){
    fetch('http://localhost:3000/snippet')
    .then(res => res.json())
    .then(data => this.snippet = data)
  },
  props: {
    msg: String,
  },
};
</script>
