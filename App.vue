<script lang="ts">
import { TUILogin } from '@tencentcloud/tui-core';
// #ifdef APP-PLUS || H5
import { TUIChatKit } from './TUIKit';
TUIChatKit.init();
// #endif

let vueVersion = 2;
// #ifdef VUE3
vueVersion = 3;
// #endif

// Required information
// You can get userSig from TencentCloud chat console for Testing TUIKit.
// Deploy production environment please get it from your server.
// View https://cloud.tencent.com/document/product/269/32688
uni.$SDKAppID = 1600006050; // Your SDKAppID
uni.$userID = '3490'; // Your userID
uni.$userSig = 'eJyrVgrxCdYrSy1SslIy0jNQ0gHzM1NS80oy0zLBwsYmljDx4pTsxIKCzBQlK0MzAyAwMzA1gMikVhRkFqUCxU1NTY2AMhDRksxckJi5kaGhoYWhoSXUlMx0oLGJUSHBXlERpmEmEZUx*oV5KTn*SZl5RZXGReXFHqaZGf5*BUbe5sae7onOobZKtQCxZjCw'; // Your userSig

export default {
  onLaunch: function () {
	 TUILogin.login({
	   SDKAppID: uni.$SDKAppID,
	   userID: uni.$userID, 
	   userSig: uni.$userSig, 
	   useUploadPlugin: true, // If you need to send rich media messages, please set to true.
	   framework: `vue${vueVersion}` // framework used vue2 / vue3
	 }).catch(() => {});
  }
};
</script>
<style>
/* common css for page */
uni-page-body,html,body,page {
  width: 100% !important;
  height: 100% !important;
  overflow: hidden;
}
</style>