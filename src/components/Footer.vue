<template>
  <div class="footer-container">
    <div class="footer-nav">
      <ul class="footer-list">
        <li class="footer-list-item">News</li>
        <li class="footer-list-item">Press</li>
        <li class="footer-list-item">FAQ</li>
        <li class="footer-list-item">Download</li>
      </ul>
    </div>
    <div class="footer-end">
      <p class="title">
        <span class="copy-sign">©</span>
        Elite SRL | Reg.Impr.PD/C.F./P.I. Intrastat IT 04342350289 -
        <a href="https://www.elite-it.com/it/privacy-policy" target="_blank">Privacy Policy</a>
      </p>
      <img src="../assets/images/footer-logo.svg" class="footer-logo"
           alt="Bolded by we-go">
    </div>
  </div>
</template>

<style lang="scss" scoped>
.footer-container {
  background-color: #0d0d0d;

  .footer-nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 60px 80px;
    border-bottom: 1px solid #222;
    @media screen and (min-width: 769px) and (max-width: 1024px) {
      padding: 60px;
    }
    @media screen and (max-width: 768px) {
      padding: 60px 40px;
    }

    .footer-list {
      display: flex;
      align-items: center;
      padding: 0;
      margin: 0;
      @media screen and (max-width: 500px) {
        margin: 0 auto;
        display: block;
      }

      .footer-list-item {
        font-family: "Grot10";
        color: #fff;
        font-weight: 300;
        font-style: normal;
        font-size: 14px;
        line-height: 1.5;
        letter-spacing: .05em;
        text-transform: uppercase;
        list-style: none;
        text-align: center;
        padding: .4em;
        transition: opacity .3s;
        cursor: pointer;

        &:hover {
          opacity: .6;
        }
      }
    }
  }

  .footer-end {
    padding: 60px 80px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    @media screen and (min-width: 769px) and (max-width: 1024px) {
      padding: 60px;
    }
    @media screen and (max-width: 768px) {
      padding: 60px 40px;
      align-items: flex-end;
    }
    @media screen and (max-width: 640px) {
      flex-direction: column;
      align-items: center;
      grid-gap: 40px;
    }

    .title {
      font-family: "Grot10";
      font-weight: 300;
      font-style: normal;
      font-size: 12px;
      color: #606060;
      text-transform: uppercase;
      letter-spacing: .05em;
      text-align: center;

      .copy-sign {
        margin-bottom: 0;
        display: inline-block;
        vertical-align: middle;
        margin-right: .25em;
        font-size: 35px;
        @media screen and (max-width: 768px) {
          display: block;
          text-align: center;
        }
        @media screen and (max-width: 640px) {
          margin-bottom: 20px;
        }
      }

      a {
        color: #606060;
        text-decoration: underline;
        transition: color .3s;

        &:hover {
          color: #d3d3d3;
        }
      }
    }

    .footer-logo {
      width: 50px;
      transition: opacity .3s;

      &:hover {
        opacity: .6;
      }
    }
  }
}
</style>