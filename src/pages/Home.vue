<template>
  <div class="home">
    <Row class="header" type="flex" align="middle">
      <div class="logo">
        <img src="../assets/img/logo.png" height="30" alt="">
        <span>普杰科技</span>人脸识别<Tag>V1.0</Tag>
      </div>
      <!-- <VmMsgPush style="margin-left:20px" :data="msgPushData"></VmMsgPush> -->
      <Dropdown class="login-info" placement="bottom-end">
        <Button type="ghost">
            <img src="../assets/img/photo.jpg" height="30" alt="">Admin
            <Icon type="arrow-down-b"></Icon>
        </Button> 
        <Dropdown-menu slot="list">
            <Dropdown-item divided><i class="fa fa-key"></i>Log out</Dropdown-item>
            <Dropdown-item divided><i class="fa fa-cog"></i>Setting</Dropdown-item>
        </Dropdown-menu>
      </Dropdown>
    </Row>   
    <div class="sidebar">
      <Menu theme="dark" width="100%" class="menu" :active-name="activeName" :accordion="true">
          <!-- <Menu-item name="Dashboard">
              <router-link to="/">
                <i class="fa fa-dashboard"></i>
                Dashboard  
              </router-link>
          </Menu-item>
          <Menu-item name="Widget">
              <router-link to="/widget">
                <i class="fa fa-cogs"></i>
                Widget  
              </router-link>
          </Menu-item>
          <Menu-item name="Panels">
              <router-link to="/panels">
                <i class="fa fa-database"></i>
                Panels
              </router-link>
          </Menu-item> -->
         
          <Menu-item name="识别记录">
              <router-link to="/imagelist">
                <i class="fa fa-photo"></i>
                识别记录  
              </router-link>
          </Menu-item>
           <Menu-item name="Editor" @click.native="refresh">
              <router-link to="/editor">
                <i class="fa fa-pencil"></i>
                人脸识别
              </router-link>
          </Menu-item> 
          <!-- <Menu-item name="Charts">
              <router-link to="/charts">
                <i class="fa fa-bar-chart"></i>
                Charts  
              </router-link>
          </Menu-item> -->
          <Submenu name="DataTable">
              <template slot="title">
                  <i class="fa fa-database"></i>
                  管理列表
              </template>
              <Menu-item name="ProjectTable">
                <router-link to="/project-table">
                  项目管理  
                </router-link>
              </Menu-item>
               <Menu-item name="AclTable">
                <router-link to="/acl-table">
                  权限组管理  
                </router-link>
              </Menu-item>
               <Menu-item name="LocksTable">
                <router-link to="/locks-table">
                  门锁管理  
                </router-link>
              </Menu-item>
              <Menu-item name="DevicesTable">
                <router-link to="/devices-table">
                  刷脸设备管理 
                </router-link>
              </Menu-item>
              <Menu-item name="EditableTable">
                <router-link to="/editable-table">
                  人员管理  
                </router-link>
              </Menu-item>
          </Submenu>
          <Submenu name="Pages">
              <template slot="title">
                  <i class="fa fa-file"></i>
                  Pages
              </template>
              <Menu-item name="Login">
                <router-link to="/login">
                  Login 
                </router-link>
              </Menu-item>
              <Menu-item name="Lockscreen">
                <router-link to="/lockscreen">
                  Lockscreen 
                </router-link>
              </Menu-item>
              <Menu-item name="Loading">
                <router-link to="/loading">
                  Loading
                </router-link>
              </Menu-item>
          </Submenu>
      </Menu>
    </div>
    <div class="main-content">
      <router-view></router-view> 
      <!-- <p class="vm-author">vue-manager designed by <a href="https://github.com/luosijie" target="_blank">Jesse Luo</a></p>  -->
    </div>
  </div>
</template>
<script>
import VmMsgPush from '@/components/vm-msg-push.vue'
export default {
  name: 'home',
  components: {
    VmMsgPush
  },
  methods:{
　　　　refresh:function(){
　　　　　　this.$router.go(0); 
　　　　}
　},
  mounted: function () {
    this.activeName = this.$route.name
    
  },
  data () {
    return {
      activeName: 'imageList',
      msgPushData: [
        {
          image: require('@/assets/img/photo.jpg'),
          from: 'JesseLuo',
          time: '2017-1-8',
          message: 'I like your website very much!'
        },
        {
          image: require('@/assets/img/photo.jpg'),
          from: 'JesseLuo',
          time: '2017-1-8',
          message: 'I like your website very much!'
        },
        {
          image: require('@/assets/img/photo.jpg'),
          from: 'JesseLuo',
          time: '2017-1-8',
          message: 'I like your website very much!'
        },
        {
          image: require('@/assets/img/photo.jpg'),
          from: 'JesseLuo',
          time: '2017-1-8',
          message: 'I like your website very much!'
        },
        {
          image: require('@/assets/img/photo.jpg'),
          from: 'JesseLuo',
          time: '2017-1-8',
          message: 'I like your website very much!'
        }
      ]
    }
  },   
}
</script>
