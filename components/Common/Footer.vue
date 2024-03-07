<!--
 * @Author       : Sun
 * @Date         : 2024-03-05 13:12:39
 * @LastEditTime : 2024-03-07 09:18:47
 * @Description  : 
 * @FilePath     : \fre123-nav\components\Common\Footer.vue
-->
<template>
	<footer class="text-left text-[#6c757d] p-6 bg-[rgba(248,249,250,1)] h-[70px]">
		<section class="flex justify-center">
			<!-- Left -->
			<div class="text-[14px] h-[30px]">
				<span class="text-[#ccc]"
					>Powered by fre123
					<!-- <a
						href="https://www.01cv.online"
						target="_blank"
						class="decoration-transparent text-[#ccc]"
						>01CV</a> -->
				</span>
			</div>
			<!-- Left -->

			<div v-if="footerConfig.right.is_show" class="flex-grow"></div>
			<!-- Right -->
			<div
				v-if="footerConfig.right.is_show && footerConfig.right.list.length > 0"
				class="flex text-[20px] text-black"
			>
				<a v-for="item in footerConfig.right.list" :href="item.url" target="_blank" class="pr-6">
					<IconsFontAwesome
						:size="item.icon_size"
						class="hover:text-[#0d6efd]"
						:icon="item.icon_class"
					/>
				</a>
			</div>
		</section>
	</footer>
</template>

<script setup lang="ts">
import { CONFIG_KEY_FOOTER, getConfigItem } from '~/stores/config'

const footerConfig = getConfigItem(CONFIG_KEY_FOOTER)
</script>

<style scoped></style>
