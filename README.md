- 使用 EmailJS 完成前端寄信功能
- 此範例已將所有 key 移除，僅提供功能實現參考
- 使用方式
  - 先去 EmailJS 註冊帳號
  - 選擇 Gmail 服務
  - 設定模板
  - 到 "帳戶" 做安全設定
  - 透過 emailjs.send() 發送信件 

程式碼參考
<pre>
<script setup>
import { onMounted } from 'vue'
import emailjs from 'emailjs-com'

console.log(emailjs)

const serviceId = ''
const templateId = '' // 選擇使用的模板 id
const publicKey = '' // 公開鑰
// const accessToken = '' // 私鑰 (目前不確定要如何帶此參數)

// 設定寄信模板中變數的值
const templateParams = {
  toName: '', // 收件人名稱
  toEmailAddress: '', // 收件人信箱
  fromName: '', // 寄件人名稱
  emailContent: '' // 信件內容
  // accessToken: '', // 私鑰
}

onMounted(() => {
  // sendEmail()
})

function sendEmail () {
  emailjs.send(serviceId, templateId, templateParams, publicKey)
    .then((res) => {
      console.log('寄信成功!!', res)
    })
    .catch((err) => {
      console.log('寄信失敗', err)
      // "API calls in strict mode, but no private key was passed"
      // “嚴格模式下API調用，但沒有傳遞私鑰”

      // Gmail_API: Request had insufficient authentication scopes
      // Gmail_API：請求的身份驗證範圍不足
    })
}
</script>
</pre>