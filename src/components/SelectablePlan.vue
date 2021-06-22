<template>
    <div>
      <div v-if=" $t('products.product'+ this.id + '.productName' + this.id) != 'products.product'+ this.id + '.productName' + this.id">
        <div class="mx-auto py-8 md:flex md:justify-between md:flex-wrap">
            <div class="w-48 bg-white rounded-lg shadow-md px-6 py-4 cursor-pointer mb-8 hover:bg-blue-100 focus:outline-none focus:shadow-outline-green">
              <div id="product">
                
                <section id="Name">
                  <div class="flex justify-between items-center mb-3">
                    <h1 class="uppercase text-base tracking-wide text-gray-700 font-bold my-2"> {{ $t('products.product'+ this.id + '.productName' + this.id)}}
                    </h1>
                  </div>
                </section>
                
                <section id="Description">
                  <div class="mb-1 text-gray-800">
                    <span class="text-base tracking-wide text-gray-700 my-2">{{ $t('products.product'+ this.id + '.productDesc' + this.id)}}</span>
                  </div>
                </section>
                
                <section id="Size">
                  <div v-if="$t('products.product'+ this.id + '.productType' + this.id) === 'Bike'">
                    <span class="text-base tracking-wide text-gray-700 my-2">
                      {{ $t('products.product'+ this.id + '.productSize' + this.id) + " " + $t('productSizeBike')}}
                    </span>
                  </div>
                  <div v-else-if="$t('products.product'+ this.id + '.productType' + this.id) === 'Part'">
                    <span class="text-base tracking-wide text-gray-700 my-2">
                      {{ $t('products.product'+ this.id + '.productSize' + this.id) + " " + $t('productSizePart')}}
                    </span>
                  </div>
                  <div v-else>
                    <span class="text-base tracking-wide text-gray-700 my-2">
                      {{ $t('productSizeOneSize')}}
                    </span>
                  </div>
                </section>

                <section id="Price">
                    <div v-if="$t('currency') === '€'">
                      <span class="text-l font-bold text-gray-700">{{  parseInt($t('products.product'+ this.id + '.productPrice' + this.id)) * 0.84 }}</span>
                      <span class="text-xl text-gray-700">{{ " " + $t('currency') }}</span>
                    </div>
                    <div v-else-if="$t('currency') === 'LKR'">
                      <span class="text-l font-bold text-gray-700">{{  parseInt($t('products.product'+ this.id + '.productPrice' + this.id)) * 198.72 }}</span>
                      <span class="text-xl text-gray-700">{{ " " + $t('currency') }}</span>
                    </div>
                    <div v-else>
                      <span class="text-l font-bold text-gray-700">{{  parseInt($t('products.product'+ this.id + '.productPrice' + this.id))}}</span>
                      <span class="text-xl text-gray-700">{{ " " + $t('currency') }}</span>
                    </div>
                </section>
              </div>
            </div>
        </div>
      </div>  
    </div>
</template>

<script>



export default {
  props: ['id'],
}
</script>

