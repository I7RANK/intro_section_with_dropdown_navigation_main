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
        ] },
        { name: "Company", subItems: [
          { name: "History", icon: "" },
          { name: "Out Team", icon: "" },
          { name: "Blog", icon: "" }
        ] },
        { name: "Careers", subItems: [] },
        { name: "About", subItems: [] },
      ]
    };
  },
};
</script>

<template>
  <div class="navbar-content">
    <nav class="main-menu">
      <ul>
        <li :key="item.name" v-for="item in navItems">
          {{ item.name }}
          <img v-if="item.subItems.length" :src="iconArrowDown" alt="">
        </li>
      </ul>
    </nav>

    <div class="sign-button-content">
      <button class="btn-sign-in"></button>
      <button class="btn-sign-out"></button>
    </div>
  </div>
</template>

<style>
.navbar-content {
  display: flex;
  flex-direction: column;
  padding: 0 0 0 20px;
}

.main-menu ul {
  padding: 0;
}

.main-menu ul li {
  list-style: none;
}
</style>
