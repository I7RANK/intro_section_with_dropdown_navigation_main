<script>
import iconArrowDown from "../assets/images/icon-arrow-down.svg";
import iconArrowUp from "../assets/images/icon-arrow-up.svg";
import iconCalendar from "../assets/images/icon-calendar.svg";
import iconPlanning from "../assets/images/icon-planning.svg";
import iconReminders from "../assets/images/icon-reminders.svg";
import iconTodo from "../assets/images/icon-todo.svg";

export default {
  data: function () {
    return {
      iconArrowDown,
      iconArrowUp,
      iconCalendar,
      iconPlanning,
      iconReminders,
      iconTodo,
      navItems: [
        { name: "Features", subItems: [
          { name: "Todo list", icon: iconTodo },
          { name: "Calendar", icon: iconCalendar },
          { name: "Reminders", icon: iconReminders },
          { name: "Planing", icon: iconPlanning }
        ],
        toggleSubItem: false },
        { name: "Company", subItems: [
          { name: "History", icon: "" },
          { name: "Out Team", icon: "" },
          { name: "Blog", icon: "" }
        ],
        toggleSubItem: false },
        { name: "Careers", subItems: [], toggleSubItem: false },
        { name: "About", subItems: [], toggleSubItem: false },
      ]
    };
  },
  methods: {
    handleToggleSubItem (item) {
      if (!item.subItems.length) return;

      item.toggleSubItem = !item.toggleSubItem;
    }
  }
};
</script>

<template>
  <div class="navbar-content">
    <nav class="main-menu">
      <ul>
        <li :key="item.name" v-for="item in navItems">
          <span class="item-name" @click="this.handleToggleSubItem(item)">
            {{ item.name }}
            <img v-if="item.subItems.length && !item.toggleSubItem" :src="iconArrowDown" alt="">
            <img v-else-if="item.subItems.length" :src="iconArrowUp" alt="">
          </span>

          <div v-if="item.toggleSubItem" class="sub-items-dropdown">
            <ul>
              <li class="sub-item-name" :key="subItem.name" v-for="subItem in item.subItems">
                <span>
                  <img v-if="subItem.icon" :src="subItem.icon" alt="">
                  {{ subItem.name }}
                </span>
              </li>
            </ul>
          </div>
        </li>
      </ul>
    </nav>

    <div class="sign-button-content">
      <button class="btn-sign-in">Login</button>
      <button class="btn-sign-out">Register</button>
    </div>
  </div>
</template>

<style>
.navbar-content {
  display: flex;
  flex-direction: column;
  padding: 0 20px;
  color: var(--medium-gray);
  font-size: .9rem;
}

.navbar-content li {
  min-height: 30px;
}

.main-menu ul {
  padding: 0;
}

.main-menu ul li span {
  cursor: pointer;
  user-select: none;
}

.navbar-content li {
  list-style: none;
}

.item-name img {
  margin: 0 15px;
}

.sub-items-dropdown {
  margin: 20px;
  transform-origin: left;
  animation: subMenuAnimation .3s ease;
}

.sub-items-dropdown .sub-item-name {
  min-height: 30px;
}

.sub-item-name img {
  height: 16px;
  width: 16px;
  margin: 0 7px 0 0;
}

.sign-button-content {
  display: flex;
  flex-direction: column;
}

.sign-button-content button {
  background: none;
  color: var(--medium-gray);
  border: none;
  height: 38px;
  border-radius: 15px;
  margin: 0 0 3px 0;
}

.sign-button-content .btn-sign-out {
  border: solid 2px var(--medium-gray);
}

@keyframes subMenuAnimation {
  from {transform: scale(0);}
  to {transform: scale(1);}
}
</style>
