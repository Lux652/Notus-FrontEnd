<template>
  <div class="footer">
    <div class="footer-top">
      <p>© 2019. Notus IT d.o.o.</p>
    </div>
    <div class="footer-bottom">
      <img class="footer-logo" src="../assets/Notus-logo-footer.svg" alt="" />
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer"
};
</script>

<style>
.footer-bottom {
  background: #081b2f;
  height: 200px;
  position: absolute;
  z-index: 1;
  left: 0;
  right: 0;
}

.footer-bottom .footer-logo {
  margin-top: 100px;
}

.footer-top {
  background: #42beb2;
  height: 100px;
  position: absolute;
  z-index: 2;
  left: 15%;
  right: 15%;
  margin-top: -2.5%;
}

.footer-top p {
  margin-top: 35px;
  color: #fff;
  font-size: 18px;
}
</style>
