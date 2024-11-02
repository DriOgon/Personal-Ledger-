<template>
  <div class="add-account">
    <h1>添加账户</h1>
    <form @submit.prevent="saveAccount">
      <div>
        <label for="accountType">账户类型:</label>
        <select v-model="accountType" id="accountType">
          <option value="银行卡">银行卡</option>
          <option value="支付宝">支付宝</option>
          <option value="微信">微信</option>
          <option value="现金">现金</option>
        </select>
      </div>
      <div>
        <label for="accountName">账户名称:</label>
        <input type="text" v-model="accountName" id="accountName" required />
      </div>
      <button type="submit">保存</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'AddAccount',
  data() {
    return {
      accountType: '银行卡',
      accountName: ''
    };
  },
  methods: {
    saveAccount() {
      // 保存账户逻辑（例如，发送到后端或存储在状态管理中）
      console.log('账户类型:', this.accountType);
      console.log('账户名称:', this.accountName);
      // 完成后跳转回主界面
      uni.navigateBack();
    }
  }
};
</script>

<style scoped>
/* 样式略 */
</style>