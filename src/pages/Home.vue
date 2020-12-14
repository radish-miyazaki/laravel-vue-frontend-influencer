<template>
  <div>
    <Header />
    <div class="album py-5 bg-light">
      <div class="container">
        <div class="row">
          <div class="col-md-4">
            <div class="card mb-4 shadow-sm">
              <img class="card-img-top" data-src="holder.js/100px225?theme=thumb&bg=55595c&fg=eceeef&text=Thumbnail" alt="Card image cap">
              <div class="card-body">
                <p class="card-text">これは写真の解説文付きのカードです。自然に説明を加えることができます。しかしこの文章は少し長いかもしれません。</p>
                <div class="d-flex justify-content-between align-items-center">
                  <div class="btn-group">
                    <button type="button" class="btn btn-sm btn-outline-secondary">見る</button>
                    <button type="button" class="btn btn-sm btn-outline-secondary">編集</button>
                  </div>
                  <small class="text-muted">9分</small>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";

export default {
  name: "Home",

  components: {
    Header,
  }

}
</script>