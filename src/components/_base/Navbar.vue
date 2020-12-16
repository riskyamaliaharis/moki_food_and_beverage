<template>
  <!-- <div>
    <router-link to="/">Home</router-link> |
    <router-link to="/product">Product</router-link> |
    <router-link to="/payment">Payment</router-link>
  </div> -->
  <nav class="navbar sticky-top navbar-expand-lg navbar-light">
    <a class="navbar-brand" href="#">
      <img
        src="../../assets/img/moki.png"
        width="100"
        height="80"
        class="d-inline-block align-top"
        alt="logo"
        rounded
      />
    </a>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav m-auto">
        <li class="nav-item active">
          <router-link to="/" class="nav-link">Home</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/product" class="nav-link">Product</router-link>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">You Cart</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Payment</a>
        </li>
      </ul>
      <form class="form-inline my-2 my-lg-0">
        <input
          class="form-control mr-sm-2"
          type="search"
          placeholder="Search"
          aria-label="Search"
        />
        <button class="btn btn-dark my-2 my-sm-0" type="submit">
          Search
        </button>
      </form>
      <div class="ml-2">
        <b-avatar
          badge
          badge-variant="success"
          src="https://placekitten.com/300/300"
        ></b-avatar>
      </div>
    </div>
  </nav>
</template>
