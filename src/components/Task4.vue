<template>
  <div class="task4-container" id="task5">
    <div class="map-container">
      <iframe
        onload="this.width=screen.width;this.height=screen.height;"
        id="gmap_canvas"
        src="https://maps.google.com/maps?q=Notus%20it%20zagreb&t=&z=17&ie=UTF8&iwloc=&output=embed"
        frameborder="0"
        scrolling="no"
        marginheight="0"
        marginwidth="0"
      ></iframe>
    </div>
    <div class="task4-text-container">
      <p class="text-first-part">
        Quas enim kakaw Graeci appellant, vitia malo quam malitias nominare.
        Idem adhuc; Idemque diviserunt naturam hominis in animum et corpus.
        Istam voluptatem, inquit, Epicurus ignorat? Duo enim genera quae erant,
        fecit tria.
      </p>
      <p class="text-second-part">
        <span>
          <b style="color:#42BEB2">Ut proverbia non nulla veriora sint quam vestra dogmata</b>
        </span>
        <br />An haec ab eo non dicuntur? Idcirco enim non desideraret, quia,
        quod dolore caret, id in voluptate est. Quoniam, si dis placet, ab
        Epicuro loqui discimus. Quid sequatur, quid repugnet, vident.
      </p>
      <button class="btn-border">
        <span>
          <b>Hover to have solid fill</b>
        </span>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Task4"
};
</script>

<style>
.map-container iframe {
  display: block;
  width: 100vw;
  height: 600px;
  max-width: 100%;
  margin: 0;
  padding: 0;
  border: 0 none;
  box-sizing: border-box;
}

.task4-text-container {
  margin-top: 4%;
  text-align: center;
}

.task4-container {
  display: grid;
  grid-template-columns: 1fr 1.8fr 1fr;
  grid-template-rows: repeat(2, 1fr);
  grid-column-gap: 0px;
  grid-row-gap: 0px;
}

.map-container {
  grid-area: 1 / 1 / 2 / 4;
}
.task4-text-container {
  grid-area: 2 / 2 / 3 / 3;
}

.text-first-part,
.text-second-part {
  text-align: center;
  font: Regular 18px Montserrat;
  color: #5c5c5c;
}
.btn-border {
  display: inline-block;
  position: relative;
  background-color: #fff;
  font-size: 18px;
  cursor: pointer;
  margin: 20px 30px;
  border: 5px solid #f89d36;
  opacity: 1;
  transition: all 0.5s linear;
}
.btn-border span {
  display: block;
  padding: 30px 20px;
  color: #081b2f;
  font-size: 18px;
}

.btn-border:hover {
  background: #f89d36;
  transition: all 0.5s linear;
}
</style>
