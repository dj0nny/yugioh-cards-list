<template>
  <div class="card">
    <span class="favorite"></span>
    <h2>{{card[0].name}}</h2>

    <div class="card__details">
      <div class="card__detailsLeft">
        <img :src="card[0].card_images[0].image_url" />
      </div>
      <div class="card__detailsRight">
        <div class="card__detailsRight__field">
         <h4>Type:</h4> {{card[0].type}}
        </div>
        <div class="card__detailsRight__field">
          <h4>Description:</h4> {{card[0].desc}}
        </div>
        <div class="card__detailsRight__field">
          <h4>Attack:</h4> {{card[0].atk}}
        </div>
        <div class="card__detailsRight__field">
          <h4>Defense:</h4> {{card[0].def}}
        </div>
        <div class="card__detailsRight__field">
          <h4>Level:</h4> {{card[0].level}}
        </div>
        <div class="card__detailsRight__field">
          <h4>Race:</h4> {{card[0].race}}
        </div>
        <div class="card__detailsRight__field">
          <h4>Attribute:</h4> {{card[0].attribute}}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    card: Object,
  },
}
</script>
