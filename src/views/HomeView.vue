<template>
  <section>
    <div class="container">
      <div class="top">
        <h1>
          Notifications <span>{{ notis.length }}</span>
        </h1>
        <button class="readall-btn">Mark all as read</button>
      </div>
      <div class="message-wrapper">
        <div
          class="notification"
          v-for="noti in notis"
          :key="notis.name"
          :class="{ unread: !noti.messageRead }"
        >
          <div class="content">

            <div class="alert">
              <p class="name">{{ noti.fullName }}</p>
              <p class="action">{{ noti.userAction }}</p>
              <p class="event">{{ noti.event }}</p>
            </div>
            <p class="time">{{ noti.time }}</p>
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
          fullName: "Mark Webber",
          profilePic: "url",
          userAction: "reacted to your recent post",
          event: "My first tournament today",
          time: "1m ago",
          messageRead: false,
          privateMessage: "",
        },
        {
          fullName: "Angela Grey",
          profilePic: "url",
          userAction: "followed you",
          event: "",
          time: "5m ago",
          messageRead: false,
          privateMessage: "",
        },
        {
          fullName: "Jacob Thompson",
          profilePic: "url",
          userAction: "has joined your group",
          event: "Chess Club",
          time: "1 day ago",
          messageRead: false,
          privateMessage: "",
        },
        {
          fullName: "Rizky Hasanuddin",
          profilePic: "url",
          userAction: "sent you a private message",
          event: "",
          time: "5 days ago",
          messageRead: true,
          privateMessage:
            "Hello, thanks for setting up the Chess Club. I've been a member for a few weeks now ",
        },
        {
          fullName: "Kimberly Smith",
          profilePic: "url",
          userAction: "commented on your picture",
          event: "",
          time: "1 week ago",
          messageRead: true,
          privateMessage: "",
        },
        {
          fullName: "Nathan Peterson",
          profilePic: "url",
          userAction: "reacted to your recent post",
          event: "5 end-game strategies to increase your win rate",
          time: "2 weeks ago",
          messageRead: true,
          privateMessage: "",
        },
        {
          fullName: "Anna Kim",
          profilePic: "url",
          userAction: "left the group",
          event: "Chess Club",
          time: "2 weeks ago",
          messageRead: true,
          privateMessage: "",
        },
      ],
    };
  },
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
  height: 50rem;
  background-color: var(--white);
  border-radius: 14px;
  padding-inline: 2rem;
  padding-top: 2rem;
  box-shadow: 0px 0px 30px 1px rgba(0, 0, 0, 0.068);
}
.top {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  width: 100%;
  height: fit-content;
  padding-bottom: 1rem;
}
.top h1{
    font-weight: 800;
    color: var(--vdblue);
}
.top h1 span{
    font-weight: 800;
    background: var(--blue);
    color: var(--white);
    font-size: .9rem;
    padding-block: .15rem;
    padding-inline: .55rem;
    border-radius: 4px;
    margin-left: .3rem;
    vertical-align: middle;
}
.readall-btn{
    color: var(--dgblue);
    background: none;
    border: none;
    outline: none;
    font-weight: 500;
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
}
.content {
  display: flex;
  flex-direction: column;
}
.alert {
  display: flex;
  column-gap: 0.5rem;
  height: fit-content;
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
}
.unread {
  background: var(--vlgblue);
}

</style>
