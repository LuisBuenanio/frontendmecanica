<template>
    <li class="unread " >
      <a href="javascript:void(0)" >
        <div class="d-flex">
          <div class="chat-user-img align-self-center me-3 ms-0" >
            <div class="avatar-xs">
              <span class="avatar-title rounded-circle bg-soft-primary text-primary">
              {{chat.destino.letra}}
              </span>
            </div>
            <span class="user-status"></span>
          </div>
          <div class="flex-grow-1 overflow-hidden">
            <h5 class="text-truncate font-size-15 mb-1">
              {{chat.destino.perfil.nombre}}
            </h5>
            <p class="chat-user-message text-truncate mb-0" >
              <i class="ri-check-double-fill align-middle me-1 ms-0 text-primary" ></i>
  
              sasaas
            </p>
          </div>
          <div class="font-size-11" >
            12 pm
          </div>
          <div class="unread-message" >
            <span class="badge badge-soft-danger rounded-pill" >kj</span>
          </div>
        </div>
      </a>
    </li>
  
  </template>
  <script>
  export default {
    props: {
      chat:{
        type:Object,
        default:()=>{}
      }
  
    },
    data() {
      return {
  
      };
    },
    computed: {
  
    },
    methods: {
  
    },
    mounted() {
  
    }
  };
  </script>
  