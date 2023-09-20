<template>


  <div class="layout-wrapper d-lg-flex">
    <!-- Start left sidebar-menu -->

    <ChatSidebar-menu :user="user" />
    <!-- end left sidebar-menu -->

    <!-- start chat-leftsidebar -->
    <ChatSidebar-start :online="online">
      <div class="chat-message-list px-2" slot="chats" data-simplebar>

        <ul class="list-unstyled chat-list chat-user-list">
          <template v-for="m in perfil.chat_perfils">
            <WidgetChat :chat="m" >
            </WidgetChat>
          </template>


        </ul>
        {{ perfil }}
      </div>
    </ChatSidebar-start>
    <!-- end chat-leftsidebar -->
    <ChatUser-chat >
    </ChatUser-chat>
    <!-- <div class="user-chat w-100 overflow-hidden text-center pt-4" >
      <img src="/chat.svg" alt="" style="margin-top:150px" width="50%">
    </div> -->
    <!-- Start User chat -->

  </div>
</template>

<script>

export default {
  name: 'IndexPage',
  data() {
    return {
      perfil: {
        chat_perfils: []
      },
      chat_actual: {
        id: '',
        chat_id: ''
      },
      user: {

      },
      online: [],
      isVisible: false,
      isLoading:true
    }
  },
  methods: {
    Logout() {
      localStorage.removeItem('userChat')
      this.$router.push('/login')
    },
    conectarSocket() {

      this.$socket.main.emit("newOnline", this.user)


    },
    async GetPerfil() {
      
      const res = await this.$api.$get('perfils/' + this.user.perfil.id)
      this.perfil = res

    },
  },
  mounted() {
    let ls = localStorage.getItem('userChat')
    let user = JSON.parse(ls)
    if (user == null) {
      this.$router.push('/login')
    }
    this.user = user
    this.$nextTick(async () => {
      await this.GetPerfil()

      this.conectarSocket()

    })
  },
  beforeDestroy() {

  }
}
</script>
