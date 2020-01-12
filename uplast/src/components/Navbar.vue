<template>
  <nav class="navbar navbar-expand-md">
    <div class="container-fluid">
      <a class="navbar-brand" href="./index.html"
        ><img src="..\assets\img\logo.png" alt="Logo"
      /></a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarCollapse"
        aria-controls="navbarCollapse"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar__burger navbar-toggler-icon"
          ><i class="fas fa-bars"></i
        ></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarCollapse">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item active">
            <a class="nav-link" href="./index.html">Заказы</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="./contacts.html">Контакты</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Помощник продаж</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Помощь</a>
          </li>
        </ul>
        <form class="form-inline mt-2 mt-md-0">
          <button
            type="button"
            class="btn nav__bar__btn__enter btn-outline-info"
            data-toggle="modal"
            data-target="#logOut"
          >
            Выход
          </button>
        </form>
      </div>
    </div>
  </nav>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
// Header

.header {
  background-color: #fff;
}

.navbar {
  background-color: #fff;

  button:focus {
    outline: none;
  }
}

.navbar-brand {
  margin-right: 100px;
}
.nav-item {
  height: 100%;
  margin-right: 45px;
}

.header {
  .nav-link {
    color: #191919;
    font-size: 12px;
    font-weight: bold;
    text-transform: uppercase;
    border-bottom: 2px solid white;
    transition: border-color 0.2s linear;

    &:first-child {
      padding-left: 120px;
    }

    &:hover {
      color: #191919;
      border-color: #0084db;
    }
  }
}

.navbar-expand-md .navbar-nav .nav-link {
  padding-left: 0px;
  padding-right: 0px;
}

.navbar-toggler {
  outline: none;
  border: none;
  &:focus {
    outline: 0;
  }
}

.navbar__burger {
  margin-top: 7px;
  font-size: 2rem;
  color: #0084db;
  outline: none;
}

.navbar-collapse {
  @media (max-width: 768px) {
    text-align: right;
  }
}

.nav__bar__btn__enter {
  @media (max-width: 768px) {
    width: 100%;
  }
}
</style>
