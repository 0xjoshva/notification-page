<template>
  <section>
    <div class="container">
      <div class="top">
        <h1>
          Notifications <span>{{}}</span>
        </h1>
        <button class="readall-btn" @click="readAll()">
          Mark all as read
        </button>
      </div>
      <div class="message-wrapper">
        <div
          class="notification"
          v-for="noti in notis"
          :key="noti.name"
          :class="{ unread: !noti.messageRead }"
        >
          <div class="content">
            <div class="row">
              <img :src="noti.profilePic" alt="" class="profilepic" />
              <div class="time-container">
                <div class="alert">
                  <p class="name">{{ noti.fullName }}</p>
                  <p class="action">{{ noti.userAction }}</p>
                  <p
                    class="event"
                    :class="{ blue: noti.event === 'Chess Club' }"
                  >
                    {{ noti.event }}
                  </p>
                  <p v-if="noti.messageRead === false" class="bullet">•</p>
                  <p v-else="noti.messageRead === true" class="bullet bullet-hidden">•</p>
                </div>
                <p class="time">{{ noti.time }}</p>
                <div class="private-message" v-if="noti.privateMessage">
                  <p>{{ noti.privateMessage }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      notis: [
        {
          fullName: "Mark Webber ",
          profilePic:
            "https://raw.githubusercontent.com/0xjoshva/notification-page/main/src/assets/avatar-mark-webber.webp",
          userAction: "reacted to your recent post ",
          event: "My first tournament today!",
          time: "1m ago",
          messageRead: false,
          privateMessage: "",
        },
        {
          fullName: "Angela Grey ",
          profilePic:
            "https://raw.githubusercontent.com/0xjoshva/notification-page/main/src/assets/avatar-angela-gray.webp",
          userAction: "followed you ",
          event: "",
          time: "5m ago",
          messageRead: false,
          privateMessage: "",
        },
        {
          fullName: "Jacob Thompson ",
          profilePic:
            "https://raw.githubusercontent.com/0xjoshva/notification-page/main/src/assets/avatar-jacob-thompson.webp",
          userAction: "has joined your group ",
          event: "Chess Club",
          time: "1 day ago",
          messageRead: false,
          privateMessage: "",
        },
        {
          fullName: "Rizky Hasanuddin ",
          profilePic:
            "https://raw.githubusercontent.com/0xjoshva/notification-page/main/src/assets/avatar-rizky-hasanuddin.webp",
          userAction: "sent you a private message ",
          event: "",
          time: "5 days ago",
          messageRead: true,
          privateMessage:
            "Hello, thanks for setting up the Chess Club. I've been a member for a few weeks now and I'm already having lots of fun and improving my game. ",
        },
        {
          fullName: "Kimberly Smith ",
          profilePic:
            "https://raw.githubusercontent.com/0xjoshva/notification-page/main/src/assets/avatar-kimberly-smith.webp",
          userAction: "commented on your picture ",
          event: "",
          time: "1 week ago",
          messageRead: true,
          privateMessage: "",
        },
        {
          fullName: "Nathan Peterson ",
          profilePic:
            "https://raw.githubusercontent.com/0xjoshva/notification-page/main/src/assets/avatar-nathan-peterson.webp",
          userAction: "reacted to your recent post ",
          event: "5 end-game strategies to increase your win rate",
          time: "2 weeks ago",
          messageRead: true,
          privateMessage: "",
        },
        {
          fullName: "Anna Kim ",
          profilePic:
            "https://raw.githubusercontent.com/0xjoshva/notification-page/main/src/assets/avatar-anna-kim.webp",
          userAction: "left the group ",
          event: "Chess Club",
          time: "2 weeks ago",
          messageRead: true,
          privateMessage: "",
        },
      ],
    };
  },
  methods: {
    readAll() {
      for (let i=0; i <= this.notis.length; i++){
        this.notis[i].messageRead = true;
      }
    },
    unreadMessages() {
      for (let i = 0; i <= this.notis.length; i++){
        if (this.notis.messageRead = false) { 
          return true;
        }
        return false;
      }
    },
    
  },
   mounted() {
     console.log()
  }
  
};
</script>
<style>
section {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
  min-height: 100vh;
  height: fit-content;
  background: var(--vlgblue);
}
.container {
  display: flex;
  flex-direction: column;
  width: 50rem;
  height: fit-content;
  min-height: 50rem;
  background-color: var(--white);
  border-radius: 14px;
  padding-inline: 2rem;
  padding-top: 2rem;
  box-shadow: 0px 0px 30px 1px rgba(0, 0, 0, 0.068);
  padding-bottom: 1rem;
}
.top {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  width: 100%;
  height: fit-content;
  padding-bottom: 1rem;
}
.top h1 {
  font-weight: 800;
  color: var(--vdblue);
}
.top h1 span {
  font-weight: 800;
  background: var(--blue);
  color: var(--white);
  font-size: 0.9rem;
  padding-block: 0.15rem;
  padding-inline: 0.55rem;
  border-radius: 4px;
  margin-left: 0.3rem;
  vertical-align: middle;
}
.readall-btn {
  color: var(--dgblue);
  background: none;
  border: none;
  outline: none;
  font-weight: 500;
}
.readall-btn:hover{
color: var(--blue);
}
.message-wrapper {
  display: flex;
  flex-direction: column;
  row-gap: 1rem;
}
.notification {
  display: flex;
  width: 100%;
  height: fit-content;
  background: var(--white);
  color: var(--gblue);
  padding: 1rem;
  border-radius: 10px;
  transition: 1s ease all;
 
}
.content {
  display: flex;
  flex-direction: column;
  column-gap: 1rem;
}
.row {
  display: flex;
  flex-direction: row;
  column-gap: 1rem;
}
.alert {
  width: 100%;
  
}
p {
  display: inline;
  word-wrap: break-word;
}
.name {
  color: var(--vdblue);
  font-weight: 800;
}
.action,
.time {
  font-weight: 500;
}
.event {
  color: var(--dgblue);
  font-weight: 650;
   margin-right: 0.3rem;
}
.profilepic {
  width: 50px;
  height: 50px;
  border-radius: 50%;
}
.unread {
  background: var(--vlgblue);
}
.blue {
  color: var(--blue) !important;
}
.time-container {
  display: flex;
  flex-direction: column;
}
.bullet {
  color: var(--red);
  font-size: 1.5rem;
  vertical-align: start;
}
.bullet-hidden{
  visibility: hidden !important;
}

.name:hover,
.event:hover {
  color: var(--blue);
}
.private-message {
  padding: .8rem;
  border: 1px solid var(--lgblue2);
  font-weight: 500;
  border-radius: 6px;
  color: var(--dgblue);
  margin-top: .6rem;
  transition: all .1s ease-in-out;
}
.private-message:hover {
  background: var(--lgblue2);
}

</style>
