<template>
  <div>
    <ul class="nav nav-tabs component-controller-nav">
      <router-link to="/captcha" tag="li" active-class="active" exact>
        <a href="#">验证码记录</a>
      </router-link>
      <router-link to="/captcha/gateway" tag="li" active-class="active">
        <a href="#">网关配置</a>
      </router-link>
      <router-link to="/captcha/template" tag="li" active-class="active">
        <a href="#">模版配置</a>
      </router-link>
    </ul>
    <router-view />
  </div>
</template>