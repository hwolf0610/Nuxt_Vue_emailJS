<template>
  <form class="contact-form" @submit.prevent="sendEmail">
    <label>Name</label>
    <input type="text" name="user_name">
    <label>Email</label>
    <input type="email" name="user_email">
    <label>Message</label>
    <textarea name="message"></textarea>
    <input type="submit" value="Send">
  </form>
</template>

<script>
import emailjs from 'emailjs-com';
export default {
  methods: {
    sendEmail: (e) => {
      emailjs.sendForm('outlook', 'template_uPT7djJ4', e.target, ' user_hnDxLeSTYEzzypf8F3AQT')
        .then((result) => {
            console.log('SUCCESS!', response.status, response.text);
        }, (error) => {
            console.log('FAILED...', error);
        });
    }
  }
}
</script>