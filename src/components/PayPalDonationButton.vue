<template>
  <div id="donate-button-container">
    <div id="donate-button"></div>
  </div>
</template>

<script>
export default {
  name: 'PayPalDonationButton',
  mounted() {
    PayPal.Donation.Button({
      env: 'production',
      hosted_button_id: 'MCMBC5LNQT3N8',
      image: {
        src: 'https://pics.paypal.com/00/s/ZjYzYTQ2YTEtNTQ4Mi00ZmRmLTk5NmQtOGM5ODU1ZGUxZDVi/file.PNG',
        alt: 'Donate with PayPal button',
        title: 'PayPal - The safer, easier way to pay online!',
      },
    }).render('#donate-button');
  },
};
</script>
