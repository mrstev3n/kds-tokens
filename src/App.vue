/* eslint-disable */
<template>
  <div class="container-fluid">
    <div class="row no-gutter">
      <!-- The image half -->
      <div class="col-md-6 d-none d-md-flex bg-image"></div>
      <!-- The content half -->
      <div class="col-md-6 bg-light">
        <div class="login d-flex align-items-center py-5">
          <!-- Demo content-->
          <div class="container">
            <div class="row">
              <div class="col-lg-10 col-xl-8 mx-auto">
                <h3 class="display-4">KDS Login Page</h3>
                <p class="text-muted mb-4">Here is a simple login page.</p>
                <form>
                  <div class="form-group mb-3">
                    <input
                      id="inputEmail"
                      type="email"
                      placeholder="Email address"
                      required=""
                      autofocus=""
                      class="form-control rounded-pill border-0 shadow-sm px-4"
                    />
                  </div>
                  <div class="form-group mb-3">
                    <input
                      id="inputPassword"
                      type="password"
                      placeholder="Password"
                      required=""
                      class="form-control rounded-pill border-0 shadow-sm px-4 text-primary"
                    />
                  </div>
                  <div class="custom-control custom-checkbox mb-3">
                    <input
                      id="customCheck1"
                      type="checkbox"
                      checked
                      class="custom-control-input"
                    />
                    <label for="customCheck1" class="custom-control-label"
                      >Remember password</label
                    >
                  </div>
                  <button
                    type="submit"
                    class="btn btn-primary btn-block text-uppercase mb-2 rounded-pill shadow-sm"
                  >
                    Sign in
                  </button>
                  <div class="text-center d-flex justify-content-between mt-4">
                    <p>
                      Already have an account ?
                      <a href="#" class="font-italic text-muted">
                        <u>Login here</u></a
                      >
                    </p>
                  </div>
                </form>
              </div>
            </div>
          </div>
          <!-- End -->
        </div>
      </div>
      <!-- End -->
    </div>
  </div>
</template>

<style lang="scss">
@import "scss/_variables.scss";
.container {
  color: $neutral-n900;
}
.display-4 {
  font-weight: 500;
  color: $primary-blue-k500;
}
.login,
.image {
  min-height: 100vh;
}
.bg-image {
  // background-color: $primary-orange-o500;
  background-image: url("assets/quote.png");
  background-size: cover;
  background-position: center center;
}
</style>
