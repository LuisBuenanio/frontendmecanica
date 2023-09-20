<template>
    <div class="user-chat w-100 overflow-hidden user-chat-show" >
      <div class="d-lg-flex">
        <!-- start chat conversation section -->
        <div class="w-100 overflow-hidden position-relative">
          <div class="p-3 p-lg-4 border-bottom user-chat-topbar">
            <div class="row align-items-center">
              <div class="col-sm-4 col-8">
                <div class="d-flex align-items-center">
                  <div class="d-block d-lg-none me-2 ms-0">
                    <a href="javascript: void(0);"
                      class="user-chat-remove text-muted font-size-16 p-2"><i class="ri-arrow-left-s-line"></i></a>
                  </div>
                  <div class="me-3 ms-0">
                    <div class="chat-user-img align-self-center">
                      <div class="avatar-xs">
                        <span class="avatar-title rounded-circle bg-soft-primary text-primary">
                          s
                        </span>
                      </div>
                    </div>
                  </div>
                  <div class="flex-grow-1 overflow-hidden">
                    <h5 class="font-size-16 mb-0 text-truncate">
                      <a href="#" class="text-reset user-profile-show">user</a>
                      <i class="ri-record-circle-fill font-size-10 text-success d-inline-block ms-1"></i>
                    </h5>
                  </div>
                </div>
              </div>
              <div class="col-sm-8 col-4">
                <ul class="list-inline user-chat-nav text-end mb-0">
                  <li class="list-inline-item">
                    <div class="dropdown">
                      <button class="btn nav-btn dropdown-toggle" type="button" data-bs-toggle="dropdown"
                        aria-haspopup="true" aria-expanded="false">
                        <i class="ri-search-line"></i>
                      </button>
                      <div class="dropdown-menu p-0 dropdown-menu-end dropdown-menu-md">
                        <div class="search-box p-2">
                          <input type="text" class="form-control bg-light border-0" placeholder="Search.." />
                        </div>
                      </div>
                    </div>
                  </li>
  
                  <li class="list-inline-item d-none d-lg-inline-block me-2 ms-0">
                    <button type="button" class="btn nav-btn" data-bs-toggle="modal" data-bs-target="#audiocallModal">
                      <i class="ri-phone-line"></i>
                    </button>
                  </li>
  
                  <li class="list-inline-item d-none d-lg-inline-block me-2 ms-0">
                    <button type="button" class="btn nav-btn" data-bs-toggle="modal" data-bs-target="#videocallModal">
                      <i class="ri-vidicon-line"></i>
                    </button>
                  </li>
  
                  <li class="list-inline-item d-none d-lg-inline-block me-2 ms-0">
                    <button type="button" class="btn nav-btn user-profile-show">
                      <i class="ri-user-2-line"></i>
                    </button>
                  </li>
  
                  <li class="list-inline-item">
                    <div class="dropdown">
                      <button class="btn nav-btn dropdown-toggle" type="button" data-bs-toggle="dropdown"
                        aria-haspopup="true" aria-expanded="false">
                        <i class="ri-more-fill"></i>
                      </button>
                      <div class="dropdown-menu dropdown-menu-end">
                        <a class="dropdown-item d-block d-lg-none user-profile-show" href="#">View profile
                          <i class="ri-user-2-line float-end text-muted"></i></a>
                        <a class="dropdown-item d-block d-lg-none" href="#" data-bs-toggle="modal"
                          data-bs-target="#audiocallModal">Audio <i class="ri-phone-line float-end text-muted"></i></a>
                        <a class="dropdown-item d-block d-lg-none" href="#" data-bs-toggle="modal"
                          data-bs-target="#videocallModal">Video
                          <i class="ri-vidicon-line float-end text-muted"></i></a>
                        <a class="dropdown-item" href="#">Archive
                          <i class="ri-archive-line float-end text-muted"></i></a>
                        <a class="dropdown-item" href="#">Muted
                          <i class="ri-volume-mute-line float-end text-muted"></i></a>
                        <a class="dropdown-item" href="#">Delete
                          <i class="ri-delete-bin-line float-end text-muted"></i></a>
                      </div>
                    </div>
                  </li>
                </ul>
              </div>
            </div>
          </div>
          <!-- end chat user head -->
  
          <!-- start chat conversation -->
          <div class="chat-conversation p-3 p-lg-4" data-simplebar="init">
  
            <ul id="scroll" class="list-unstyled mb-0">
  
              <li>
                <div  class="conversation-list px-2 m-0">
                  <div class="chat-avatar">
                    <div class="chat-user-img align-self-center">
                      <div class="avatar-xs">
                        <span class="avatar-title rounded-circle bg-soft-primary text-primary">
                          G
                        </span>
                      </div>
                    </div>
                  </div>
  
                  <div class="user-chat-content">
                    <div class="ctext-wrap">
                      <div class="ctext-wrap-content">
                        <p class="mb-0">
                          Escribiendo
                          <span class="animate-typing">
                            <span class="dot"></span>
                            <span class="dot"></span>
                            <span class="dot"></span>
                          </span>
                        </p>
                      </div>
                    </div>
  
                    <div class="conversation-name">
                      A
                    </div>
                  </div>
                </div>
              </li>
            </ul>
          </div>
          <!-- end chat conversation end -->
  
          <!-- start chat input section -->
          <div class="chat-input-section p-3 p-lg-4 border-top mb-0">
            <div class="row g-0">
              <div class="col">
                <input type="text"
                  class="form-control form-control-lg bg-light border-light" placeholder="Escribe un mensaje..."
                   />
              </div>
              <div class="col-auto">
                <div class="chat-input-links ms-md-2 me-md-0">
                  <ul class="list-inline mb-0">
                    <li class="list-inline-item" data-bs-toggle="tooltip" data-bs-placement="top" title="Emoji">
                      <button type="button" class="btn btn-link text-decoration-none font-size-16 btn-lg waves-effect">
                        <i class="ri-emotion-happy-line"></i>
                      </button>
                    </li>
                    <li class="list-inline-item" data-bs-toggle="tooltip" data-bs-placement="top" title="Attached File">
                      <button type="button" class="btn btn-link text-decoration-none font-size-16 btn-lg waves-effect">
                        <i class="ri-attachment-line"></i>
                      </button>
                    </li>
                    <li class="list-inline-item">
                      <button type="button"
                        class="btn btn-primary font-size-16 btn-lg chat-send waves-effect waves-light">
                        <i class="ri-send-plane-2-fill"></i>
                      </button>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
          <!-- end chat input section -->
        </div>
        <!-- end chat conversation section -->
  
  
      </div>
      <!-- End User chat -->
  
      <!-- end modal -->
    </div>
  </template>
  
  <script>
  export default {
    props: {
  
    },
    data() {
      return {
  
      };
    },
    watch: {
  
    },
    computed: {
  
    },
    methods: {
  
      bottomScroll() {
        document.getElementById("scroll").scrollTop =
          document.getElementById("scroll").scrollHeight;
      },
  
    },
    mounted() {
  
    },
    beforeDestroy() { },
  };
  </script>
  <style>
  #scroll {
    overflow-y: scroll;
    height: 70vh;
    min-height: 70vh;
    max-height: 70vh;
    width: 100%;
  }
  
  #scroll::-webkit-scrollbar {
    -webkit-appearance: none;
  }
  
  #scroll::-webkit-scrollbar:vertical {
    width: 10px;
  }
  
  #scroll::-webkit-scrollbar-button:increment,
  #scroll::-webkit-scrollbar-button {
    display: none;
  }
  
  #scroll::-webkit-scrollbar:horizontal {
    height: 10px;
  }
  
  #scroll::-webkit-scrollbar-thumb {
    background-color: #8f8f8fc7;
    border-radius: 20px;
    border: 1px solid #cececea2;
  }
  
  #scroll::-webkit-scrollbar-track {
    border-radius: 10px;
  }
  
  .chat-conversation {
    overflow: hidden;
    padding: 0;
  }
  </style>
  