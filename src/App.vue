<template>
  <header>
    <div class="col-md-12">
      <div class="col-md-12 header-icons">
        <div
          data-bind="click: toggleMenu"
          class="lpp-bt-menu"
          id="div-lpp-bt-menu"
        >
          <i></i> <i></i> <i></i>
        </div>
        <div id="div-lpp-logo" class="lpp-logo"></div>
        <div
          id="div-lpp-ico-negocios-empresa"
          class="lpp-ico-negocios-empresa"
        ></div>
        <span
          id="span-lpp-header-title"
          class="lpp-header-title"
          data-bind="widgetLocaleText: 'headerTitle'"
          >Portal de Benefícios</span
        >
        <div
          id="div-lpp-header-profile"
          data-bind="css: {'lpp-header-profile--open': showProfileMenu}"
          class="lpp-header-profile"
        >
          <span id="span-lpp-infos-user">
            <span data-bind="widgetLocaleText: 'headerProfileHello'"
              >Olá,
            </span>
            <strong data-bind="text: $data.firstName">Maurício</strong>
            <br />
            <strong data-bind="text: company().commercialName"
              >PORTAL PARTNER TEST</strong
            >
            <br />
          </span>
          <div
            id="div-profile-thumb"
            class="profile-thumb"
            data-bind="click: toggleProfileMenu"
          >
            <i class="icon-user"></i>
          </div>
          <i
            id="i-lpp-profile-thumb-chevron"
            class="icon-chevron-down"
            data-bind="click: toggleProfileMenu"
          ></i>
          <i
            id="i-lpp-mobile-toggle-menu-bt"
            class="icon-user"
            data-bind="click: toggleProfileMenu"
          ></i>
          <div id="div-lpp-profile-menu" class="profile-menu">
            <div
              id="div-lpp-profile-menu-content"
              class="profile-menu__content"
            >
              <i class="up"></i>
              <div class="col-md-12">
                <h1
                  id="h1-lpp-profile-menu-content-title"
                  data-bind="text: company().commercialName"
                >
                  PORTAL PARTNER TEST
                </h1>
              </div>
              <hr />
              <div class="col-md-12 menus">
                <a
                  data-bind="ccLink: 'perfil'"
                  href="/perfil"
                  id="a-lpp-profile-menu-content-my-account"
                  data-gtm-event-category="livelo:portal-empresas:geral"
                  data-gtm-event-action="clique:header"
                  data-gtm-event-label="perfil"
                  ><i class="icon-user"></i
                  ><span
                    data-bind="widgetLocaleText: 'headerProfileOptionMyAccount'"
                    >Perfil</span
                  ></a
                >
                <a
                  href="javascript:;"
                  id="a-lpp-profile-menu-content-logout"
                  data-bind="event: {click: logout.bind($parent)}"
                  data-gtm-event-category="livelo:portal-empresas:geral"
                  data-gtm-event-action="clique:header"
                  data-gtm-event-label="sair"
                  ><i class="icon-log-out"></i
                  ><span
                    data-bind="widgetLocaleText: 'headerProfileOptionLogout'"
                    >Sair</span
                  ></a
                >
              </div>
              <div class="clearfix"></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "app",
};
</script>

<style>
header {
  height: 100px;
  width: 100%;
  background-color: #666;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 901;
  transition: all 0.2s ease-out;
  background: #666;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
* {
  box-sizing: border-box;
}

body * {
  -webkit-text-rendering: optimizeLegibility !important;
  -moz-text-rendering: optimizeLegibility !important;
  -ms-text-rendering: optimizeLegibility !important;
  -o-text-rendering: optimizeLegibility !important;
  text-rendering: optimizeLegibility !important;
  -webkit-font-smoothing: antialiased !important;
  -moz-font-smoothing: antialiased !important;
  -ms-font-smoothing: antialiased !important;
  -o-font-smoothing: antialiased !important;
  font-smoothing: antialiased !important;
}
body #page:not(.no-header) header {
  height: 100px;
  width: 100%;
  background-color: #666;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 901;
  transition: all 0.2s ease-out;
}
header .lpp-bt-menu {
  pointer-events: auto;
  height: 20px;
  width: 33px;
  margin-top: 28px;
  margin-right: 24px;
  float: left;
  position: relative;
  display: none;
}
header .lpp-logo {
  width: 70px;
  height: 70px;
  background: url("https://a7069719c1dev-store.occa.ocs.oraclecloud.com/file/general/pink.svg")
    no-repeat center center;
  background-size: cover;
  margin-top: 14px;
  float: left;
}
header .lpp-ico-negocios-empresa {
  width: 48px;
  height: 48px;
  margin-left: 20px;
  background: url("https://a7069719c1dev-store.occa.ocs.oraclecloud.com/file/general/negocios-empresa.svg")
    no-repeat center center;
  background-size: cover;
  margin-top: 26px;
  float: left;
}
header .lpp-header-title {
  font: 18px "MuseoSans";
  font-weight: 500;
  color: #fff;
  float: left;
  margin: 37px 0 0 10px;
}
header .lpp-header-profile {
  position: relative;
  float: right;
  margin-right: 30px;
  margin-top: 30px;
}
header .lpp-header-profile > span {
  text-align: right;
  color: #fff;
  font: 14px "MuseoSans";
  font-weight: normal;
  display: block;
  float: left;
}
header .lpp-header-profile div.profile-thumb {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  background-color: #fff;
  float: left;
  margin-left: 10px;
  margin-right: 15px;
  text-align: center;
  padding-top: 5px;
  cursor: pointer;
}
header .lpp-header-profile > i.icon-chevron-down {
  float: right;
  color: #fff;
  font-size: 18px;
  display: block;
  margin-top: 10px;
  cursor: pointer;
}
header .lpp-header-profile div.profile-menu {
  display: none;
  position: absolute;
  top: 41px;
  right: -15px;
  width: 330px;
  height: auto;
}
@media (min-width: 992px) {
  .col-md-12 {
    width: 100%;
  }
  .col-md-1,
  .col-md-2,
  .col-md-3,
  .col-md-4,
  .col-md-5,
  .col-md-6,
  .col-md-7,
  .col-md-8,
  .col-md-9,
  .col-md-10,
  .col-md-11,
  .col-md-12 {
    float: left;
  }
  .col-xs-1,
  .col-sm-1,
  .col-md-1,
  .col-lg-1,
  .col-xs-2,
  .col-sm-2,
  .col-md-2,
  .col-lg-2,
  .col-xs-3,
  .col-sm-3,
  .col-md-3,
  .col-lg-3,
  .col-xs-4,
  .col-sm-4,
  .col-md-4,
  .col-lg-4,
  .col-xs-5,
  .col-sm-5,
  .col-md-5,
  .col-lg-5,
  .col-xs-6,
  .col-sm-6,
  .col-md-6,
  .col-lg-6,
  .col-xs-7,
  .col-sm-7,
  .col-md-7,
  .col-lg-7,
  .col-xs-8,
  .col-sm-8,
  .col-md-8,
  .col-lg-8,
  .col-xs-9,
  .col-sm-9,
  .col-md-9,
  .col-lg-9,
  .col-xs-10,
  .col-sm-10,
  .col-md-10,
  .col-lg-10,
  .col-xs-11,
  .col-sm-11,
  .col-md-11,
  .col-lg-11,
  .col-xs-12,
  .col-sm-12,
  .col-md-12,
  .col-lg-12 {
    position: relative;
    min-height: 1px;
    padding-right: 15px;
    padding-left: 15px;
  }
}
</style>
