<script>

    export let card;

</script>

<div class="card">
  <div class="card-image">
    <img src="{card.url}" class="img-responsive" alt="{card.altText}">
  </div>
  <div class="card-header">
    <div class="card-title h5">{card.title}</div>
    <div class="card-subtitle text-gray">{card.subTitle}</div>
  </div>
  <div class="card-body">
      <p>{card.body}</p>
  </div>
  <div class="card-footer">
    <!-- <button class="btn btn-primary">{card.footer}</button> -->
    <p>🤣 {card.footer}</p>
  </div>
</div>