<template>
  <div class="budget-input-page">
    <h1>填写预算</h1>

    <div class="input-group">
      <label for="monthlyBudgetInput">月支:</label>
      <input 
        id="monthlyBudgetInput" 
        v-model.number="monthlyExpenseInput" 
        type="number" 
        placeholder="请输入月支"
      >
    </div>
    
    <div class="input-group">
      <label for="annualBudgetInput">年支:</label>
      <input 
        id="annualBudgetInput" 
        v-model.number="annualExpenseInput" 
        type="number" 
        placeholder="请输入年支"
      >
    </div>
    
    <button @click="saveBudget">保存</button>
  </div>
</template>

<script>
export default {
  name: 'BudgetInput',
  data() {
    return {
      monthlyExpenseInput: null, // 改为空值表示数字
      annualExpenseInput: null   // 改为空值表示数字
    };
  },
  methods: {
    saveBudget() {
      // 在控制台输出用户输入的数值
      console.log(`月支出: ${this.monthlyExpenseInput}, 年支出: ${this.annualExpenseInput}`);
      
      // 保存成功后返回上一页
      uni.showToast({
        title: '保存成功',
        icon: 'success'
      });
      uni.navigateBack();
    }
  }
};
</script>

<style scoped>
.budget-input-page {
  padding: 20px;
}

.input-group {
  margin-bottom: 20px;
}

label {
  font-weight: bold;
}

input {
  width: 100%;
  padding: 10px;
  margin-top: 5px;
  box-sizing: border-box;
}

button {
  background-color: #4CAF50;
  color: white;
  padding: 10px;
  width: 100%;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}
</style>