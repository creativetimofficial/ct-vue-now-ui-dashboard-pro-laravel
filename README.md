# [Vue Now UI Dashboard Pro Laravel](https://vue-now-ui-dashboard-pro-laravel.creative-tim.com/?ref=vnudpl-readme) [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social&logo=twitter)](https://twitter.com/home?status=Vue%Now%Ui%20Dashboard%20Pro%20Laravel%E2%9D%A4%EF%B8%8F%0Ahttps%3A//vue-now-ui-dashboard-pro-laravel.creative-tim.com/%20%23%vue%20%23%now%ui%20%23design%20%23dashboard%20%23laravel%20%23pro%20via%20%40CreativeTim)

![version](https://img.shields.io/badge/version-1.0.0-blue.svg) [![GitHub issues open](https://img.shields.io/github/issues/creativetimofficial/ct-vue-now-ui-dashboard-pro-laravel.svg?maxAge=2592000)](https://github.com/creativetimofficial/ct-vue-now-ui-dashboard-pro-laravel/issues?q=is%3Aopen+is%3Aissue) [![GitHub issues closed](https://img.shields.io/github/issues-closed-raw/creativetimofficial/ct-vue-now-ui-dashboard-pro-laravel/ct-vue-now-ui-dashboard-pro-laravel.svg?maxAge=2592000)](https://github.com/creativetimofficial/ct-vue-now-ui-dashboard-pro-laravel/issues?q=is%3Aissue+is%3Aclosed)

_Frontend version_: Now UI Dashboard v1.5.0. More info at https://www.creative-tim.com/product/now-ui-dashboard-pro

_Vue version_: Vue Now UI Dashboard v1.2.0. More info at https://www.creative-tim.com/product/vue-now-ui-dashboard-pro

![Product Image](https://raw.githubusercontent.com/creativetimofficial/public-assets/master/vue-now-ui-dashboard-laravel-pro/intro.gif)

What if you could go from frontend to fullstack in an instant when building your app? We partnered with [UPDIVISION](https://updivision.com) to bring you Vue Now UI Dashboard PRO Laravel, the ultimate fullstack resource. Vue Now UI Dashboard PRO Laravel comes not only with a huge number of UI components and a Vue Now UI frontend, but also with an API-powered Laravel backend.

# Download

For the PRO version of the project you will download the .zip file from the Creative Tim site and extract it.

You will get two project folders: one for the Laravel API project and one for the Vue frontend.

# Laravel API Setup

## Introduction

JSON:API is a specification for how a client should request that resources be fetched or modified, and how a server should respond to those requests. It is designed to minimize both the number of requests and the amount of data transmitted between clients and servers. This efficiency is achieved without compromising readability, flexibility, or discoverability.

[Click here to go to the JSON:API docs](https://explore.postman.com/api/6357/laravel-jsonapi)

## Prerequisites

The Laravel JSON:API project requires a working Apache/Nginx local environment with PHP, Composer and MySQL.

If you don't already have a local development environment, use one of the following links:

- Windows: [How to install WAMP on Windows](https://updivision.com/blog/post/beginner-s-guide-to-setting-up-your-local-development-environment-on-windows)
- Linux: [How to install LAMP on Linux](https://howtoubuntu.org/how-to-install-lamp-on-ubuntu)
- Mac: [How to install MAMP on MAC](https://wpshout.com/quick-guides/how-to-install-mamp-on-your-mac/)
- Install Composer: [https://getcomposer.org/doc/00-intro.md](https://getcomposer.org/doc/00-intro.md)

Install Composer: https://getcomposer.org/doc/00-intro.md

Install Node: https://nodejs.org/ (version 8.11.0+ recommended)

Install NPM: https://www.npmjs.com/get-npm

Install VueCLI: https://cli.vuejs.org/guide/installation.html

## Laravel API Project Installation

1. Navigate in your Laravel API project folder: `cd your-laravel-json-api-project`
2. Install project dependencies: `composer install`
3. Create a new .env file: `cp .env.example .env`
4. Add your own database credentials in the .env file in DB_DATABASE, DB_USERNAME, DB_PASSWORD
5. Create users table: `php artisan migrate --seed`
6. Generate application key: `php artisan key:generate`
7. Install Laravel Passport: `php artisan passport:install`
8. Add your own mailtrap.io credentials in MAIL_USERNAME and MAIL_PASSWORD in the .env file

## Vue Now UI Dashboard Project Installation

1. Navigate to your Vue Now UI Dashboard project folder: `cd your-vue-now-ui-dashbord-project`
2. Install project dependencies: `npm install`
3. Create a new .env file: `cp .env.example .env`
4. `VUE_APP_BASE_URL` should contain the URL of your Vue Now Ui Dashboard Project (eg. http://localhost:8080/)
5. `VUE_APP_API_BASE_URL` should contain the URL of your Laravel JSON:API Project. (eg. http://localhost:3000/api/v1)
6. Run `npm run dev` to start the application in a local development environment or `npm run build` to build release distributables.

## Usage

To start testing the Pro theme, register as a user or log in using one of the default users:

- admin type - **admin@jsonapi.com** with the password **secret**
- creator type - **creator@jsonapi.com** with the password **secret**
- member type - **member@jsonapi.com** with the password **secret**

In addition to the features included in the free theme, the Pro theme also has a role management example with an updated user management, as well as tag management, category management and item management examples. All the necessary files are installed out of the box and all the needed routes are added to `src\routes\routes.js`. Keep in mind that all the features can be viewed once you log in using the credentials provided above or by registering your own user.

Each role has a different privilege level and can perform a certain number of actions according to this level.

A **member type** user can log in, update his profile and view a list of added items.
A **creator type** user can log in, update his profile and perform actions on categories, tags and items.
A **admin type** user can log in, update his profile and perform actions on categories, tags, items, roles and users.

### Dashboard

You can access the dashboard either by using the "**Dashboards/Dashboard**" link in the left sidebar or by adding **/dashboard** in the URL.

### Login

The login functionality is fully implemented in our theme helping you to start your project in no time. To login into dashboard you just have to add **/login** in the URL and fill the login form with one of the credentials (user: **admin@jsonapi.com**, **creator@jsonapi.com**, **member@jsonapi.com** and password: **secret**).

The `src\pages\Dashboard\Pages\Login.vue` is the Vue component which handles the login functinality. You can easily adapt it to your needs.

It uses the auth store located in `src\store\modules\auth.js`.

### Login Card

```
<div class="col-md-4 ml-auto mr-auto" style="margin-top: 35px">
  <form role="form" @submit.prevent="handleSubmit()">
    <card class="card-login card-plain">
      <div slot="header">
        <div class="logo-container">
          <img src="/img/now-logo.png" alt="" />
        </div>
      </div>

      <div>
        <fg-input
          v-model="email"
          name="email"
          class="no-border form-control-lg"
          placeholder="Email"
          addon-left-icon="now-ui-icons ui-1_email-85"
          :error="apiValidationErrors.email"
        >
        </fg-input>

        <fg-input
          v-model="password"
          type="password"
          name="password"
          class="no-border form-control-lg"
          placeholder="Password"
          addon-left-icon="now-ui-icons ui-1_lock-circle-open"
          :error="apiValidationErrors.password"
        >
        </fg-input>
      </div>

      <div slot="footer">
        <n-button native-type="submit" type="primary" round block>
          Get Started
        </n-button>
        <div class="pull-left">
          <h6>
            <router-link class="link footer-link" to="/register">
              Create Account
            </router-link>
          </h6>
        </div>

        <div class="pull-right">
          <h6>
            <a href="/password/reset" class="link footer-link"
              >Forgot password?</a
            >
          </h6>
        </div>
      </div>
    </card>
  </form>
</div>
```

### Register

The register functionality is fully implemented in our theme helping you to start your project in no time. To register a new user you just have to add **/register** in the URL or click on register link from login page and fill the register form with user details.

The `src\pages\Dashboard\Pages\Register.vue` is the Vue component which handles the login functinality. You can easily extend it to your needs.

It uses the auth store located in `src\store\modules\auth.js`.

#### Register card

```
<div class="col-lg-4 mr-auto">
  <form role="form" @submit.prevent="handleSubmit">
    <card class="card-signup text-center" no-footer-line>
      <template slot="header">
        <h4 class="card-title">Register</h4>
        <div class="social">
          <button class="btn btn-icon btn-round btn-twitter">
            <i class="fab fa-twitter"></i>
          </button>
          <button class="btn btn-icon btn-round btn-dribbble">
            <i class="fab fa-dribbble"></i>
          </button>
          <button class="btn btn-icon btn-round btn-facebook">
            <i class="fab fa-facebook"> </i>
          </button>
          <h5 class="card-description">or be classical</h5>
        </div>
      </template>

      <fg-input
        v-model="name"
        name="name"
        placeholder="Name"
        addon-left-icon="now-ui-icons users_circle-08"
        :error="apiValidationErrors.name"
      >
      </fg-input>

      <fg-input
        v-model="email"
        name="email"
        placeholder="Email"
        addon-left-icon="now-ui-icons ui-1_email-85"
        :error="apiValidationErrors.email"
      >
      </fg-input>

      <fg-input
        v-model="password"
        name="password"
        placeholder="Password"
        addon-left-icon="now-ui-icons ui-1_lock-circle-open"
        type="password"
        :error="apiValidationErrors.password"
      >
      </fg-input>

      <fg-input
        v-model="password_confirmation"
        name="confirmPassword"
        placeholder="Confirm Password"
        addon-left-icon="now-ui-icons ui-1_lock-circle-open"
        type="password"
        :error="apiValidationErrors.password_confirmation"
      >
      </fg-input>

      <checkbox class="text-left" v-model="boolean">
        I agree to the <a href="#something">terms and conditions</a>.
      </checkbox>

      <n-button
        slot="footer"
        type="primary"
        native-type="submit"
        round
        size="lg"
      >
        Get Started
      </n-button>
    </card>
  </form>
</div>
```

### Profile edit

You have the option to edit the current logged in user's profile information (name, email, profile picture) and password. To access this page, just click the "**Examples/Profile**" link in the left sidebar or add **/examples/user-profile** in the URL.

The `src\pages\Dashboard\Examples\UserProfile` is the folder with Vue components that handle the update of the user information and password.

#### Edit profile component

```
<template>
  <div class="row">
    <div class="col-lg-8">
      <div>
        <user-edit-card :user="user" />
      </div>
      <div class="mt-5">
        <user-password-card :user="user" />
      </div>
    </div>
    <div class="col-lg-4">
      <user-card />
    </div>
  </div>
</template>

<script>
import UserEditCard from "@/pages/Dashboard/Examples/UserProfile/EditProfileCard.vue";
import UserPasswordCard from "@/pages/Dashboard/Examples/UserProfile/EditPasswordCard.vue";
import UserCard from "@/pages/Dashboard/Pages/UserProfile/UserCard.vue";

export default {
  name: "user-profile-example",

  components: {
    "user-card": UserCard,
    "user-edit-card": UserEditCard,
    "user-password-card": UserPasswordCard,
  },

  data() {
    return {
      user: {
        type: "profile",
        name: null,
        email: null,
        profile_image: null,
      },
    };
  },

  created() {
    this.getProfile();
  },

  methods: {
    async getProfile() {
      await this.$store.dispatch("profile/me");
      this.user = await this.$store.getters["profile/me"];
    },
  },
};
</script>
```

#### Edit password component

```
<template>
  <div class="card">
    <div class="card-header">
      <h3>Change Password</h3>
    </div>
    <div class="card-body">
      <form ref="password_form" @submit.prevent="handleChangePassword">
        <fg-input
          v-model="password"
          type="password"
          name="new_password"
          autocomplete="on"
          class="mb-3"
          prepend-icon="fa fa-key"
          placeholder="New Password"
          addon-left-icon="now-ui-icons ui-1_lock-circle-open"
          :error="apiValidationErrors.password"
        />

        <fg-input
          v-model="password_confirmation"
          type="password"
          name="confirm_password"
          autocomplete="on"
          class="mb-3"
          prepend-icon="fa fa-key"
          placeholder="Confirm Password"
          addon-left-icon="now-ui-icons ui-1_lock-circle-open"
          :error="apiValidationErrors.password_confirmation"
        />
        <div class="my-4">
          <n-button
            type="button"
            class="btn btn-sm btn-primary"
            native-type="submit"
          >
            Change Password
          </n-button>
        </div>
      </form>
    </div>
  </div>
</template>
<script>
import formMixin from "@/mixins/form-mixin";

export default {
  name: "UserPasswordCard",

  mixins: [formMixin],

  props: {
    user: Object,
  },

  data() {
    return {
      password: null,
      password_confirmation: null,
    };
  },

  methods: {
    async handleChangePassword() {
      if (this.$isDemo == 1 && ["1", "2", "3"].includes(this.user.id)) {
        await this.$store.dispatch(
          "alerts/error",
          "You are not allowed to change data of default users."
        );
        return;
      }
      this.user.password = this.password;
      this.user.password_confirmation = this.password_confirmation;

      try {
        this.resetApiValidation();
        await this.$store.dispatch("users/update", this.user);
        this.$refs["password_form"].reset();

        await this.$store.dispatch(
          "alerts/success",
          "Password changed successfully."
        );
      } catch (error) {
        await this.$store.dispatch(
          "alerts/error",
          "Oops, something went wrong!"
        );
        this.setApiValidation(error.response.data.errors);
      }
    },
  },
};
</script>

```

### Role management

The Pro theme allows you to add user roles. By default, the theme comes with **Admin**, **Creator** and **Member** roles. To access the role management example click the "**Examples/Role Management**" link in the left sidebar or add **/examples/role-management/list-roles** to the URL. Here you can add/edit new roles.
To add a new role, click the "**Add role**" button. To edit an existing role, click the dotted menu (available on every table row) and then click "**Edit**". In both cases, you will be directed to a form which allows you to modify the name and description of a role.

The store used for role functionality is found in `src\store\modules\roles-module.vue`

You can find the compoments for role functionality in `src\pages\Dashboard\Examples\RoleManagement` folder.

#### List page

```
<div>
  <div
    class="col-12 d-flex justify-content-center justify-content-sm-between flex-wrap"
  >
    <el-select
      class="select-primary mb-3"
      style="width: 200px"
      name="pages"
      v-model="pagination.perPage"
      placeholder="Per page"
    >
      <el-option
        class="select-default"
        v-for="item in pagination.perPageOptions"
        :key="item"
        :label="item"
        :value="item"
      >
      </el-option>
    </el-select>
    <fg-input>
      <el-input
        v-model="query"
        type="search"
        class="mb-3"
        clearable
        prefix-icon="el-icon-search"
        style="width: 200px"
        placeholder="Search..."
        aria-controls="datatables"
      >
      </el-input>
    </fg-input>
  </div>
  <el-table
    stripe
    style="width: 100%"
    :data="tableData"
    @sort-change="sortChange"
  >
    <div slot="empty" v-if="loading">
      <img src="/img/loading.gif" style="height: 100px; width: 100px" />
    </div>
    <el-table-column
      v-for="column in tableColumns"
      :key="column.label"
      :min-width="column.minWidth"
      :prop="column.prop"
      :label="column.label"
      sortable="custom"
    >
    </el-table-column>
    <el-table-column :min-width="135" fixed="right" label="Actions">
      <div
        slot-scope="{ row }"
        class="table-actions"
        style="margin-left: 10px"
      >
        <el-tooltip content="Edit" :open-delay="300" placement="top">
          <n-button
            @click.native="editRole(row.id)"
            type="info"
            size="sm"
            round
            icon
          >
            <i class="now-ui-icons ui-2_settings-90"></i>
          </n-button>
        </el-tooltip>

        <el-tooltip content="Delete" :open-delay="300" placement="top">
          <n-button
            @click.native="deleteRole(row.id)"
            class="remove"
            type="danger"
            size="sm"
            round
            icon
          >
            <i class="fa fa-times"></i>
          </n-button>
        </el-tooltip>
      </div>
    </el-table-column>
  </el-table>
</div>
```

#### Add/edit role

```
<div class="card-body">
  <form ref="profile_form" @submit.prevent="handleSubmit">
    <label>Name</label>
    <fg-input
      addon-left-icon="now-ui-icons users_circle-08"
      v-model="role.name"
      :error="apiValidationErrors.name"
    />

    <div class="my-4">
      <n-button
        type="button"
        class="btn btn-sm btn-primary"
        native-type="submit"
      >
        Update Role
      </n-button>
    </div>
  </form>
</div>
```

### User management

The theme comes with an out of the box user management option. To access this option ,click the "**Examples/User Management**" link in the left sidebar or add **/examples/user-management/list-users** to the URL.
The first thing you will see is a list of existing users. You can add new ones by clicking the "**Add user**" button (above the table on the right). On the Add user page, you will find a form which allows you to fill out the user`s name, email, role and password.

The store used for role functionality is found in `src\store\modules\users-module.vue`

You can find the compoments for role functionality in `src\pages\Dashboard\Examples\UserManagement` folder.

Once you add more users, the list will grow and for every user you will have edit and delete options (access these options by clicking the three dotted menu that appears at the end of every row).

```
<div>
  <div
    class="col-12 d-flex justify-content-center justify-content-sm-between flex-wrap"
  >
    <el-select
      class="select-primary mb-3"
      style="width: 200px"
      name="pages"
      v-model="pagination.perPage"
      placeholder="Per page"
    >
      <el-option
        class="select-default"
        v-for="item in pagination.perPageOptions"
        :key="item"
        :label="item"
        :value="item"
      >
      </el-option>
    </el-select>
    <fg-input>
      <el-input
        v-model="query"
        type="search"
        class="mb-3"
        clearable
        prefix-icon="el-icon-search"
        style="width: 200px"
        placeholder="Search..."
        aria-controls="datatables"
      >
      </el-input>
    </fg-input>
  </div>
  <el-table
    stripe
    style="width: 100%"
    :data="tableData"
    @sort-change="sortChange"
  >
    <div slot="empty" v-if="loading">
      <img src="/img/loading.gif" style="height: 100px; width: 100px" />
    </div>
    <el-table-column label="Author" max-width="100px">
      <template v-slot="{ row }">
        <img
          v-if="row.profile_image"
          :src="row.profile_image"
          class="avatar rounded-circle mr-3"
        />
      </template>
    </el-table-column>

    <el-table-column
      label="Name"
      min-width="110px"
      prop="name"
      sortable="custom"
    />

    <el-table-column
      label="Email"
      min-width="120px"
      prop="email"
      sortable="custom"
    />

    <el-table-column
      label="Role"
      min-width="120px"
      prop="roles.name"
      sortable="custom"
    >
      <template v-slot="{ row }">
        <span>{{ row.roles[0].name }}</span>
      </template>
    </el-table-column>

    <el-table-column
      label="Created At"
      prop="created_at"
      min-width="150px"
      sortable="custom"
    />

    <el-table-column :min-width="135" fixed="right" label="Actions">
      <div
        slot-scope="{ row }"
        class="table-actions"
        style="margin-left: 10px"
      >
        <el-tooltip content="Edit" :open-delay="300" placement="top">
          <n-button
            @click.native="editUser(row.id)"
            type="info"
            size="sm"
            round
            icon
          >
            <i class="now-ui-icons ui-2_settings-90"></i>
          </n-button>
        </el-tooltip>

        <el-tooltip content="Delete" :open-delay="300" placement="top">
          <n-button
            @click.native="deleteUser(row.id)"
            class="remove"
            type="danger"
            size="sm"
            round
            icon
          >
            <i class="fa fa-times"></i>
          </n-button>
        </el-tooltip>
      </div>
    </el-table-column>
  </el-table>
</div>
```

### Tag management

Out of the box you will have an example of tag management (for the cases in which you are developing a blog or a shop). To access this example, click the "**Examples/Tag Management**" link in the left sidebar or add **/examples/tag-management/list-tags** to the URL.
You can add and edit tags here, but you can only delete them if they are not attached to any items.

The store used for role functionality is found in `src\store\modules\tags-module.vue`

You can find the compoments for role functionality in `src\pages\Dashboard\Examples\TagManagement` folder.

```
<div>
  <div
    class="col-12 d-flex justify-content-center justify-content-sm-between flex-wrap"
  >
    <el-select
      class="select-primary mb-3"
      style="width: 200px"
      name="pages"
      v-model="pagination.perPage"
      placeholder="Per page"
    >
      <el-option
        class="select-default"
        v-for="item in pagination.perPageOptions"
        :key="item"
        :label="item"
        :value="item"
      >
      </el-option>
    </el-select>
    <fg-input>
      <el-input
        v-model="query"
        type="search"
        class="mb-3"
        clearable
        prefix-icon="el-icon-search"
        style="width: 200px"
        placeholder="Search..."
        aria-controls="datatables"
      >
      </el-input>
    </fg-input>
  </div>
  <el-table
    stripe
    style="width: 100%"
    :data="tableData"
    @sort-change="sortChange"
  >
    <div slot="empty" v-if="loading">
      <img src="/img/loading.gif" style="height: 100px; width: 100px" />
    </div>

    <el-table-column
      label="Name"
      min-width="110px"
      prop="name"
      sortable="custom"
    />

    <el-table-column
      label="Color"
      min-width="130px"
      prop="color"
      sortable="custom"
    >
      <template slot-scope="{ row }">
        <span
          class="badge badge-default"
          :style="{ backgroundColor: row.color }"
          >{{ row.name }}</span
        >
      </template>
    </el-table-column>

    <el-table-column
      label="Created At"
      prop="created_at"
      min-width="150px"
      sortable="custom"
    />

    <el-table-column :min-width="135" fixed="right" label="Actions">
      <div
        slot-scope="{ row }"
        class="table-actions"
        style="margin-left: 10px"
      >
        <el-tooltip content="Edit" :open-delay="300" placement="top">
          <n-button
            @click.native="editTag(row.id)"
            type="info"
            size="sm"
            round
            icon
          >
            <i class="now-ui-icons ui-2_settings-90"></i>
          </n-button>
        </el-tooltip>

        <el-tooltip content="Delete" :open-delay="300" placement="top">
          <n-button
            @click.native="deleteTag(row.id)"
            class="remove"
            type="danger"
            size="sm"
            round
            icon
          >
            <i class="fa fa-times"></i>
          </n-button>
        </el-tooltip>
      </div>
    </el-table-column>
  </el-table>
</div>
```

### Category management

Out of the box you will have an example of category management (for the cases in which you are developing a blog or a shop). To access this example, click the "**Examples/Category Management**" link in the left sidebar or add **/examples/category-management/list-categories** to the URL.
You can add and edit categories here, but you can only delete them if they are not attached to any items.

The store used for category functionality is found in `src\store\modules\categories-module.vue`

You can find the compoments for category functionality in `src\pages\Dashboard\Examples\CategoryManagement` folder.

```
<div>
  <div
    class="col-12 d-flex justify-content-center justify-content-sm-between flex-wrap"
  >
    <el-select
      class="select-primary mb-3"
      style="width: 200px"
      name="pages"
      v-model="pagination.perPage"
      placeholder="Per page"
    >
      <el-option
        class="select-default"
        v-for="item in pagination.perPageOptions"
        :key="item"
        :label="item"
        :value="item"
      >
      </el-option>
    </el-select>
    <fg-input>
      <el-input
        v-model="query"
        type="search"
        class="mb-3"
        clearable
        prefix-icon="el-icon-search"
        style="width: 200px"
        placeholder="Search..."
        aria-controls="datatables"
      >
      </el-input>
    </fg-input>
  </div>
  <el-table
    stripe
    style="width: 100%"
    :data="tableData"
    @sort-change="sortChange"
  >
    <div slot="empty" v-if="loading">
      <img src="/img/loading.gif" style="height: 100px; width: 100px" />
    </div>

    <el-table-column
      label="Name"
      min-width="110px"
      prop="name"
      sortable="custom"
    />

    <el-table-column
      label="Description"
      min-width="130px"
      prop="description"
      sortable="custom"
    />

    <el-table-column
      label="Created At"
      prop="created_at"
      min-width="150px"
      sortable="custom"
    />

    <el-table-column :min-width="135" fixed="right" label="Actions">
      <div
        slot-scope="{ row }"
        class="table-actions"
        style="margin-left: 10px"
      >
        <el-tooltip content="Edit" :open-delay="300" placement="top">
          <n-button
            @click.native="editCategory(row.id)"
            type="info"
            size="sm"
            round
            icon
          >
            <i class="now-ui-icons ui-2_settings-90"></i>
          </n-button>
        </el-tooltip>

        <el-tooltip content="Delete" :open-delay="300" placement="top">
          <n-button
            @click.native="deleteCategory(row.id)"
            class="remove"
            type="danger"
            size="sm"
            round
            icon
          >
            <i class="fa fa-times"></i>
          </n-button>
        </el-tooltip>
      </div>
    </el-table-column>
  </el-table>
</div>
```

### Item management

Item management is the most advanced example included in the Pro theme, because every item has a picture, belongs to a category and has multiple tags. To access this example click the "**Examples/Item Management**" link in the left sidebar or add **/examples/item-management/list-items** to the URL.
Here you can manage the items. A list of items will appear once you start adding them (to access the add page click "**Add item**").
On the add page, besides the Name and Description fields (which are present in most of the CRUD examples) you can see a category dropdown, which contains the categories you added, a file input and a tag multi select. If you did not add any categories or tags, please go to the corresponding sections (category management, tag management) and add some.

The store used for roles functionality is found in `src\store\modules\items-module.vue`

You can find the compoments for items functionality in `src\pages\Dashboard\Examples\ItemManagement` folder.

#### List Items

```
<div>
  <div
    class="col-12 d-flex justify-content-center justify-content-sm-between flex-wrap"
  >
    <el-select
      class="select-primary mb-3"
      style="width: 200px"
      name="pages"
      v-model="pagination.perPage"
      placeholder="Per page"
    >
      <el-option
        class="select-default"
        v-for="item in pagination.perPageOptions"
        :key="item"
        :label="item"
        :value="item"
      >
      </el-option>
    </el-select>
    <fg-input>
      <el-input
        v-model="query"
        type="search"
        class="mb-3"
        clearable
        prefix-icon="el-icon-search"
        style="width: 200px"
        placeholder="Search..."
        aria-controls="datatables"
      >
      </el-input>
    </fg-input>
  </div>
  <el-table
    stripe
    style="width: 100%"
    :data="tableData"
    @sort-change="sortChange"
  >
    <div slot="empty" v-if="loading">
      <img src="/img/loading.gif" style="height: 100px; width: 100px" />
    </div>

    <el-table-column
      label="Name"
      min-width="130px"
      prop="name"
      sortable="custom"
    />

    <el-table-column
      label="Category"
      min-width="140px"
      prop="category.name"
      sortable="custom"
    />

    <el-table-column label="Picture" min-width="150px">
      <template v-slot="{ row }">
        <img
          v-if="row.image"
          :src="row.image"
          style="width: 100px; height: auto"
          alt="avatar"
        />
      </template>
    </el-table-column>

    <el-table-column
      label="Tags"
      min-width="170px"
      max-width="400px"
      prop="tags.name"
      sortable="custom"
    >
      <template slot-scope="{ row }">
        <span
          v-for="(tag, index) in row.tags"
          :key="'tag' + index"
          class="badge badge-default"
          :style="{ backgroundColor: tag.color, margin: '.1rem' }"
          >{{ tag.name }}</span
        >
      </template>
    </el-table-column>

    <el-table-column
      label="Created At"
      prop="created_at"
      min-width="160px"
      sortable="custom"
    />

    <el-table-column :min-width="135" fixed="right" label="Actions">
      <div
        slot-scope="{ row }"
        class="table-actions"
        style="margin-left: 10px"
      >
        <el-tooltip content="Edit" :open-delay="300" placement="top">
          <n-button
            @click.native="editItem(row.id)"
            type="info"
            size="sm"
            round
            icon
          >
            <i class="now-ui-icons ui-2_settings-90"></i>
          </n-button>
        </el-tooltip>

        <el-tooltip content="Delete" :open-delay="300" placement="top">
          <n-button
            @click.native="deleteItem(row.id)"
            class="remove"
            type="danger"
            size="sm"
            round
            icon
          >
            <i class="fa fa-times"></i>
          </n-button>
        </el-tooltip>
      </div>
    </el-table-column>
  </el-table>
</div>
```

#### Add/Edit Item

```
<div class="card-body">
  <form ref="profile_form" @submit.prevent="handleSubmit">
    <div class="form-group">
      <label class="form-control-label"> Picture </label>
      <div v-if="image" class="profile-image card-img pb-4">
        <img :src="`${image}`" class="profile-image now-ui-image" />
      </div>
      <div v-else class="profile-image">
        <img src="/img/placeholder.jpg" class="now-ui-image" />
      </div>
      <div class="image-upload">
        <n-button
          v-if="image"
          type="button"
          class="btn btn-sm btn-danger"
          @click.native="removeImage"
        >
          <i slot="label" class="now-ui-icons ui-1_simple-remove"></i>
          Remove
        </n-button>

        <n-button type="button" class="btn btn-sm btn-primary">
          <label
            v-if="!image"
            class="mb-0"
            style="color: white"
            >Select image</label
          >
          <label
            v-else
            class="mb-0"
            style="color: white"
            >Change</label
          >
          <input
            id="imageInput"
            ref="imageInput"
            accept="image/*"
            type="file"
            style="display: none"
            @input="onSelectFile"
          />
        </n-button>
      </div>
    </div>
    <validation-error :error="apiValidationErrors.attachment" />

    <label>Name</label>
    <fg-input
      v-model="item.name"
      name="name"
      addon-left-icon="now-ui-icons users_circle-08"
      :error="apiValidationErrors.name"
    />

    <div class="md-layout spacing">
      <label class="md-layout-item md-size-25 md-form-label">
        Description
      </label>
      <div class="md-layout-item">
        <ckeditor
          :editor="editor"
          v-model="item.description"
          :config="editorConfig"
        />
      </div>
    </div>
    <validation-error :error="apiValidationErrors.excerpt" />

    <label style="display: flex">Category</label>
    <el-select
      name="category"
      v-model="item.category.id"
      prepend-icon="fas fa-user"
      placeholder="Select..."
      style="display: flex"
    >
      <el-option
        v-for="single_category in all_categories"
        :key="single_category.id"
        :value="single_category.id"
        :label="single_category.name"
      >
      </el-option>
    </el-select>

    <label>Tags</label>
    <el-select
      v-model="tags"
      multiple
      placeholder="Select..."
      style="display: flex"
    >
      <el-option
        v-for="single_tag in all_tags"
        :key="single_tag.id"
        :value="single_tag.id"
        :label="single_tag.name"
      >
      </el-option>
    </el-select>

    <fg-input label="Status" class="mt-2">
      <radio label="published" v-model="item.status" class="mb-3">
        Published
      </radio>
      <radio label="draft" v-model="item.status" class="mb-3">
        Draft
      </radio>
      <radio label="archive" v-model="item.status" class="mb-3">
        Archive
      </radio>
    </fg-input>

    <label style="display: flex">Show on homepage?</label>
    <n-switch class="mt-2" v-model="item.is_on_homepage"></n-switch>

    <fg-input label="Date" class="mt-2">
      <el-date-picker
        type="date"
        placeholder="Date Picker"
        v-model="item.date_at"
      >
      </el-date-picker
    ></fg-input>

    <validation-error :error="apiValidationErrors.date_at" />

    <div class="my-4">
      <n-button
        type="button"
        class="btn btn-sm btn-primary"
        native-type="submit"
      >
        Update Item
      </n-button>
    </div>
  </form>
</div>
```

## Table of Contents

- [Versions](#versions)
- [Demo](#demo)
- [Documentation](#documentation)
- [File Structure](#file-structure)
- [Browser Support](#browser-support)
- [Resources](#resources)
- [Reporting Issues](#reporting-issues)
- [Licensing](#licensing)
- [Useful Links](#useful-links)

## Versions

[<img src="https://github.com/creativetimofficial/public-assets/blob/master/logos/html-logo.jpg" height="80" />](#)
[<img src="https://github.com/creativetimofficial/public-assets/blob/master/logos/laravel_logo.png" height="80" />](#)
[<img src="https://github.com/creativetimofficial/public-assets/blob/master/logos/vue.jpg" height="80" />](#)
[<img src="https://github.com/creativetimofficial/public-assets/blob/master/logos/json-api.png" height="75" />](#)

| HTML                                                                                                                                                                                           | Laravel                                                                                                                                                                                                           |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [![Now UI Dashboard Pro HTML](https://s3.amazonaws.com/creativetim_bucket/products/72/thumb/opt_nudp_thumbnail.jpg)](https://www.creative-tim.com/product/now-ui-dashboard-pro?ref=vnudpl-readme) | [![Now UI Dashboard Pro Laravel](https://s3.amazonaws.com/creativetim_bucket/products/210/thumb/opt_nudp_laravel_thumbnail.jpg)](https://www.creative-tim.com/product/now-ui-dashboard-pro-laravel?ref=vnudpl-readme) |

| Vue                                                                                                                                                                                                        | Vue & Laravel                                                                                                                                                                                                                  |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [![Vue Now UI Dashboard Pro HTML](https://s3.amazonaws.com/creativetim_bucket/products/79/thumb/opt_nudp_vue_thumbnail.jpg)](https://www.creative-tim.com/product/vue-now-ui-dashboard-pro?ref=vnudpl-readme) | [![Vue Now UI Dashboard Pro Laravel ](https://s3.amazonaws.com/creativetim_bucket/products/353/thumb/opt_adp_vue_laravel_thumbnail.jpg)](https://www.creative-tim.com/product/vue-now-ui-dashboard-pro-laravel?ref=vnudpl-readme) |

## Demo

| Register                                                                                                                                                                                                                   | Login                                                                                                                                                                                                             | Dashboard                                                                                                                                                                                                            |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [![Register](https://raw.githubusercontent.com/creativetimofficial/public-assets/master/vue-now-ui-dashboard-laravel-pro/register.png)](https://vue-now-ui-dashboard-pro-laravel.creative-tim.com/register?ref=vnudpl-readme) | [![Login](https://raw.githubusercontent.com/creativetimofficial/public-assets/master/vue-now-ui-dashboard-laravel-pro/login.png)](https://vue-now-ui-dashboard-pro-laravel.creative-tim.com/login?ref=vnudpl-readme) | [![Dashboard](https://raw.githubusercontent.com/creativetimofficial/public-assets/master/vue-now-ui-dashboard-laravel-pro/dashboard.png)](https://vue-now-ui-dashboard-pro-laravel.creative-tim.com/?ref=vnudpl-readme) |

| Profile Page                                                                                                                                                                                                                               | Users Page                                                                                                                                                                                                                                           | Tables Page                                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [![Profile Page](https://raw.githubusercontent.com/creativetimofficial/public-assets/master/vue-now-ui-dashboard-laravel-pro/profile.png)](https://vue-now-ui-dashboard-pro-laravel.creative-tim.com/examples/user-profile?ref=vnudpl-readme) | [![Users Page](https://raw.githubusercontent.com/creativetimofficial/public-assets/master/vue-now-ui-dashboard-laravel-pro/users.png)](https://vue-now-ui-dashboard-pro-laravel.creative-tim.com/examples/user-management/list-users?ref=vnudpl-readme) | [![Tables Page](https://raw.githubusercontent.com/creativetimofficial/public-assets/master/vue-now-ui-dashboard-laravel-pro/table.png)](https://vue-now-ui-dashboard-pro-laravel.creative-tim.com/table-list/paginated?ref=vnudpl-readme) |

[View More](https://vue-now-ui-dashboard-pro-laravel.creative-tim.com/?ref=vnudpl-readme)

## Documentation

The documentation for the Vue Now UI Dashboard PRO Laravel is hosted at our [website](https://vue-now-ui-dashboard-pro-laravel.creative-tim.com/documentation/#/getting-started?ref=vnudpl-github-readme).

## File Structure

Within the download you'll find the following directories and files:

```
├───vue-now-ui-dashboard-pro
│   App.vue
│   dashboard-plugin.js
│   globalComponents.js
│   globalDirectives.js
│   main.js
│   polyfills.js
│   registerServiceWorker.js
│
├───assets
│   ├───css
│   │       demo.css
│   │
│   ├───fonts
│   │       nucleo-outline.eot
│   │       nucleo-outline.ttf
│   │       nucleo-outline.woff
│   │       nucleo-outline.woff2
│   │
│   └───sass
│       │   now-ui-dashboard.scss
│       │
│       └───now-ui-dashboard
│           │   _alerts.scss
│           │   _badges.scss
│           │   _buttons.scss
│           │   _cards.scss
│           │   _carousel.scss
│           │   _checkboxes-radio.scss
│           │   _dropdown.scss
│           │   _example-pages.scss
│           │   _fixed-plugin.scss
│           │   _footers.scss
│           │   _images.scss
│           │   _info-areas.scss
│           │   _inputs.scss
│           │   _misc.scss
│           │   _mixins.scss
│           │   _modals.scss
│           │   _navbar.scss
│           │   _nucleo-outline.scss
│           │   _page-header.scss
│           │   _pagination.scss
│           │   _pills.scss
│           │   _popups.scss
│           │   _progress.scss
│           │   _responsive.scss
│           │   _sections.scss
│           │   _sidebar-and-main-panel.scss
│           │   _social-buttons.scss
│           │   _tables.scss
│           │   _tabs.scss
│           │   _timeline.scss
│           │   _typography.scss
│           │   _variables.scss
│           │
│           ├───cards
│           ├───element-ui-plugins
│           ├───mixins
│           └───plugins
├───axios
│       index.js
│
├───components
│   │   AnimatedNumber.vue
│   │   Badge.vue
│   │   Button.vue
│   │   Dropdown.vue
│   │   index.js
│   │   isDemo.js
│   │   LoadingPanel.vue
│   │   Modal.vue
│   │   Pagination.vue
│   │   Progress.vue
│   │   Slider.vue
│   │   Switch.vue
│   │   Table.vue
│   │   ValidationError.vue
│   │
│   ├───Breadcrumb
│   │       Breadcrumb.vue
│   │       BreadcrumbItem.vue
│   │       RouteBreadcrumb.vue
│   │
│   ├───Cards
│   │       Card.vue
│   │       StatsCard.vue
│   │
│   ├───Charts
│   │       BarChart.js
│   │       LineChart.js
│   │       utils.js
│   │
│   ├───Collapse
│   │       Collapse.vue
│   │       CollapseItem.vue
│   │
│   ├───Inputs
│   │       Checkbox.vue
│   │       formGroupInput.vue
│   │       IconCheckbox.vue
│   │       Radio.vue
│   │
│   ├───Navbar
│   │       Navbar.vue
│   │       NavbarToggleButton.vue
│   │
│   ├───NotificationPlugin
│   │       index.js
│   │       Notification.vue
│   │       Notifications.vue
│   │
│   ├───SidebarPlugin
│   │       index.js
│   │       SideBar.vue
│   │       SidebarItem.vue
│   │
│   ├───Tabs
│   │       Tab.vue
│   │       Tabs.vue
│   │
│   ├───Timeline
│   │       TimeLine.vue
│   │       TimeLineItem.vue
│   │
│   ├───Wizard
│   │       throttle.js
│   │       Wizard.vue
│   │       WizardTab.vue
│   │
│   └───WorldMap
│           AsyncWorldMap.vue
│           WorldMap.vue
│           world_map.js
│
├───directives
│       click-ouside.js
│
├───middleware
│       auth.js
│       guest.js
│
├───mixins
│       form-mixin.js
│
├───pages
│   ├───Dashboard
│   │   │   Charts.vue
│   │   │   DefaultHeader.vue
│   │   │   Widgets.vue
│   │   │
│   │   ├───Calendar
│   │   │       Calendar.vue
│   │   │       CalendarHeader.vue
│   │   │       CalendarRoute.vue
│   │   │
│   │   ├───Components
│   │   │   │   Buttons.vue
│   │   │   │   GridSystem.vue
│   │   │   │   Icons.vue
│   │   │   │   Notifications.vue
│   │   │   │   Panels.vue
│   │   │   │   SweetAlert.vue
│   │   │   │   Typography.vue
│   │   │   │
│   │   │   └───Headers
│   │   │           SweetAlertHeader.vue
│   │   │
│   │   ├───Dashboard
│   │   │   │   Dashboard.vue
│   │   │   │   DashboardHeader.vue
│   │   │   │   HeaderChart.js
│   │   │   │
│   │   │   └───Stats
│   │   │           Task.vue
│   │   │           TaskList.vue
│   │   │
│   │   ├───Examples
│   │   │   │   UserProfile.vue
│   │   │   │
│   │   │   ├───CategoryManagement
│   │   │   │       AddCategoryPage.vue
│   │   │   │       EditCategoryPage.vue
│   │   │   │       ListCategoryPage.vue
│   │   │   │
│   │   │   ├───ItemManagement
│   │   │   │       AddItemPage.vue
│   │   │   │       EditItemPage.vue
│   │   │   │       ListItemPage.vue
│   │   │   │
│   │   │   ├───RoleManagement
│   │   │   │       AddRolePage.vue
│   │   │   │       EditRolePage.vue
│   │   │   │       ListRolePage.vue
│   │   │   │
│   │   │   ├───TagManagement
│   │   │   │       AddTagPage.vue
│   │   │   │       EditTagPage.vue
│   │   │   │       ListTagPage.vue
│   │   │   │
│   │   │   ├───UserManagement
│   │   │   │       AddUserPage.vue
│   │   │   │       EditUserPage.vue
│   │   │   │       ListUserPage.vue
│   │   │   │
│   │   │   └───UserProfile
│   │   │           EditPasswordCard.vue
│   │   │           EditProfileCard.vue
│   │   │
│   │   ├───Forms
│   │   │   │   ExtendedForms.vue
│   │   │   │   RegularForms.vue
│   │   │   │   ValidationForms.vue
│   │   │   │   Wizard.vue
│   │   │   │
│   │   │   ├───ValidationForms
│   │   │   │       LoginForm.vue
│   │   │   │       RangeValidationForm.vue
│   │   │   │       RegisterForm.vue
│   │   │   │       TypeValidationForm.vue
│   │   │   │
│   │   │   └───Wizard
│   │   │           FirstStep.vue
│   │   │           SecondStep.vue
│   │   │           ThirdStep.vue
│   │   │
│   │   ├───Layout
│   │   │   │   Content.vue
│   │   │   │   ContentFooter.vue
│   │   │   │   DashboardLayout.vue
│   │   │   │   LoadingMainPanel.vue
│   │   │   │   TopNavbar.vue
│   │   │   │
│   │   │   └───Extra
│   │   │           MobileMenu.vue
│   │   │           SidebarSharePlugin.vue
│   │   │           UserMenu.vue
│   │   │
│   │   ├───Maps
│   │   │       API_KEY.js
│   │   │       FullScreenMap.vue
│   │   │       GoogleMaps.vue
│   │   │       VectorMaps.vue
│   │   │       VectorMapsHeader.vue
│   │   │       WorldMap.vue
│   │   │       world_map.js
│   │   │
│   │   ├───Pages
│   │   │   │   AuthLayout.vue
│   │   │   │   Lock.vue
│   │   │   │   Login.vue
│   │   │   │   Pricing.vue
│   │   │   │   Register.vue
│   │   │   │   TimeLinePage.vue
│   │   │   │   UserProfile.vue
│   │   │   │
│   │   │   └───UserProfile
│   │   │           EditProfileForm.vue
│   │   │           UserCard.vue
│   │   │
│   │   ├───Password
│   │   │       Email.vue
│   │   │       Reset.vue
│   │   │
│   │   └───Tables
│   │       │   ExtendedTables.vue
│   │       │   PaginatedTables.vue
│   │       │   RegularTables.vue
│   │       │   users.js
│   │       │
│   │       └───ExtendedTables
│   │               ShoppingTable.vue
│   │
│   └───GeneralViews
│           NotFoundPage.vue
│
├───routes
│       index.js
│       routes.js
│
├───store
│   │   index.js
│   │
│   ├───modules
│   │       alerts-module.js
│   │       auth.js
│   │       categories-module.js
│   │       items-module.js
│   │       profile-module.js
│   │       reset.js
│   │       roles-module.js
│   │       tags-module.js
│   │       users-module.js
│   │
│   └───services
│           categories-service.js
│           items-service.js
│           profile-service.js
│           roles-service.js
│           tags-service.js
│           users-service.js
│
└───util
        throttle.js
```

## Browser Support

At present, we officially aim to support the last two versions of the following browsers:

<img src="https://github.com/creativetimofficial/public-assets/blob/master/logos/chrome-logo.png?raw=true" width="64" height="64"> <img src="https://raw.githubusercontent.com/creativetimofficial/public-assets/master/logos/firefox-logo.png" width="64" height="64"> <img src="https://raw.githubusercontent.com/creativetimofficial/public-assets/master/logos/edge-logo.png" width="64" height="64"> <img src="https://raw.githubusercontent.com/creativetimofficial/public-assets/master/logos/safari-logo.png" width="64" height="64"> <img src="https://raw.githubusercontent.com/creativetimofficial/public-assets/master/logos/opera-logo.png" width="64" height="64">

## Resources

- Demo: <https://vue-now-ui-dashboard-pro-laravel.creative-tim.com/?ref=vnudpl-readme>
- Download Page: <https://www.creative-tim.com/product/vue-now-ui-dashboard-pro-laravel?ref=vnudpl-readme>
- Documentation: <https://vue-now-ui-dashboard-pro-laravel.creative-tim.com/documentation/#/getting-started?ref=vnudpl-readme>
- License Agreement: <https://www.creative-tim.com/license>
- Support: <https://www.creative-tim.com/contact-us>
- Issues: [Github Issues Page](https://github.com/creativetimofficial/ct-vue-now-ui-dashboard-pro-laravel/issues)
- **Dashboards:**

| HTML                                                                                                                                                                                           | Laravel                                                                                                                                                                                                           |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [![Now UI Dashboard Pro HTML](https://s3.amazonaws.com/creativetim_bucket/products/72/thumb/opt_nudp_thumbnail.jpg)](https://www.creative-tim.com/product/now-ui-dashboard-pro?ref=vnudpl-readme) | [![Now UI Dashboard Pro Laravel](https://s3.amazonaws.com/creativetim_bucket/products/210/thumb/opt_nudp_laravel_thumbnail.jpg)](https://www.creative-tim.com/product/now-ui-dashboard-pro-laravel?ref=vnudpl-readme) |


| Vue                                                                                                                                                                                                        | Vue & Laravel                                                                                                                                                                                                                 |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [![Vue Now UI Dashboard Pro HTML](https://s3.amazonaws.com/creativetim_bucket/products/79/thumb/opt_nudp_vue_thumbnail.jpg)](https://www.creative-tim.com/product/vue-now-ui-dashboard-pro?ref=vnudpl-readme) | [![Vue Now UI Dashboard Pro Laravel ](https://s3.amazonaws.com/creativetim_bucket/products/353/thumb/opt_adp_vue_laravel_thumbnail.jpg)](https://www.creative-tim.com/product/vue-now-ui-dashboard-pro-laravel?ref=vnudpl-readme) |


## Change log

Please see the [changelog](CHANGELOG.md) for more information on what has changed recently.

## Credits

- [Creative Tim](https://creative-tim.com/?ref=vnudpl-readme)
- [UPDIVISION](https://updivision.com)

## Reporting Issues

We use GitHub Issues as the official bug tracker for the Now UI Kit. Here are some advices for our users that want to report an issue:

1. Make sure that you are using the latest version of the Now UI Kit. Check the CHANGELOG from your dashboard on our [website](https://www.creative-tim.com/?ref=vnudpl-readme).
2. Providing us reproducible steps for the issue will shorten the time it takes for it to be fixed.
3. Some issues may be browser specific, so specifying in what browser you encountered the issue might help.

## Licensing

- Copyright 2020 Creative Tim (https://www.creative-tim.com/license?ref=vnudpl-readme)

- Licensed under MIT (https://github.com/creativetimofficial/vue-now-ui-dashboard/blob/master/LICENSE.md)

## Useful Links

- [Tutorials](https://www.youtube.com/channel/UCVyTG4sCw-rOvB9oHkzZD1w?ref=vnudpl-readme)
- [Affiliate Program](https://www.creative-tim.com/affiliates/new?ref=vnudpl-readme) (earn money)
- [Blog Creative Tim](http://blog.creative-tim.com/?ref=vnudpl-readme)
- [Free Products](https://www.creative-tim.com/bootstrap-themes/free?ref=vnudpl-readme) from Creative Tim
- [Premium Products](https://www.creative-tim.com/bootstrap-themes/premium?ref=vnudpl-readme) from Creative Tim
- [React Products](https://www.creative-tim.com/bootstrap-themes/react-themes?ref=vnudpl-readme) from Creative Tim
- [Angular Products](https://www.creative-tim.com/bootstrap-themes/angular-themes?ref=vnudpl-readme) from Creative Tim
- [VueJS Products](https://www.creative-tim.com/bootstrap-themes/vuejs-themes?ref=vnudpl-readme) from Creative Tim
- [More products](https://www.creative-tim.com/bootstrap-themes?ref=vnudpl-readme) from Creative Tim
- Check our Bundles [here](https://www.creative-tim.com/bundles?ref=vnudpl-readme)

## Social Media

### Creative Tim:

Twitter: <https://twitter.com/CreativeTim?ref=vnudpl-readme>

Facebook: <https://www.facebook.com/CreativeTim?ref=vnudpl-readme>

Dribbble: <https://dribbble.com/creativetim?ref=vnudpl-readme>

Instagram: <https://www.instagram.com/CreativeTimOfficial?ref=vnudpl-readme>

### Updivision:

Twitter: <https://twitter.com/updivision?ref=vnudpl-readme>

Facebook: <https://www.facebook.com/updivision?ref=vnudpl-readme>

Linkedin: <https://www.linkedin.com/company/updivision?ref=vnudpl-readme>

Updivision Blog: <https://updivision.com/blog/?ref=vnudpl-readme>

## Credits

- [Creative Tim](https://creative-tim.com/?ref=vnudpl-readme)
- [UPDIVISION](https://updivision.com)
