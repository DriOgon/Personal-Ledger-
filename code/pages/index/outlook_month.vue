<template>
  <div class="financial-report">
    <h1>月度财务报表</h1>
    
	<!-- 年份和月份选择器 -->
    <div class="date-selector">
      <div class="year-selector">
        <label for="year-select">选择年份:</label>
        <select id="year-select" v-model="currentYear" @change="fetchMonthlyData">
          <option v-for="year in years" :key="year" :value="year">
            {{ year }}
          </option>
        </select>
      </div>
      <div class="month-selector">
        <label for="month-select">选择月份:</label>
        <select id="month-select" v-model="currentMonth" @change="fetchMonthlyData">
          <option v-for="month in months" :key="month" :value="month">
            {{ month }}月
          </option>
        </select>
      </div>
    </div>
	
    <!-- 月度总账单 -->
    <section class="monthly-total">
      <h2>月度总账单</h2>
      <ul>
        <li>月度支出: 2000</li>
        <li>月度收入: 3000</li>
        <li>月度结余: 1000</li>
      </ul>
    </section>

    <!-- 月度总预算 -->
    <section class="monthly-budget">
      <h2>月度总预算</h2>
	  <button @click="navigateToBudget">编辑预算</button>
      <ul>
        <li>剩余预算: 500</li>
        <li>月度预算: 3500</li>
        <li>月度支出: 2000</li>
        <li>日均可用: 100</li>
      </ul>
    </section>

    <!-- 收支账户 -->
    <section class="accounts">
      <h2>收支账户</h2>
	  <button @click="navigateToAccount">添加账户</button>
      <ul>
        <li>系统账户: 张三</li>
      </ul>
    </section>
	<!-- 跳转到年度财务报表页面的按钮 -->
	<button @click="navigateToYearlyReport">查看年度财务报表</button>
  </div>
</template>

<script>
export default {
  name: 'FinancialReport',
  data() {
    return {
      monthlyTotalExpenses: '0.00',
      monthlyTotalIncome: '0.00',
      monthlyTotalBalance: '0.00',
      remainingBudget: '3000.00',
      monthlyBudget: '3000.00',
      monthlyBudgetExpenses: '0.00',
      dailyAvailable: '103.44',
      systemAccount: '0.00'
    };
  }
};
</script>

<style scoped>
.financial-report {
  font-family: Arial, sans-serif;
  padding: 20px;
}

.financial-report h1 {
  text-align: center;
}

.financial-report section {
  margin-bottom: 20px;
}

.financial-report ul {
  list-style-type: none;
  padding: 0;
}

.financial-report li {
  background: #f9f9f9;
  margin: 5px 0;
  padding: 10px;
  border: 1px solid #ddd;
}
</style>

<script>


export default {
  name: 'FinancialReport',
  data() {
    const currentYear = new Date().getFullYear();
    return {
      currentYear: currentYear,
      currentMonth: new Date().getMonth() + 1, // 当前月份，1-12
      years: Array.from({length: 10}, (v, k) => currentYear -  k), // 生成当前年份前后5年的年份数组
      months: Array.from({length: 12}, (v, k) => k + 1) // 生成1-12的月份数组
      // ... 其他数据属性
    };
  },
  methods: {
      fetchMonthlyData() {
        // 您的 fetchMonthlyData 方法保持不变
      },
      navigateToYearlyReport() {
        uni.navigateTo({
          url: '/pages/index/outlook_year'
        });
      },
      navigateToBudget() {
        uni.navigateTo({
          url: '/pages/index/budget-input'
        });
      },
	  navigateToAccount() {
	    uni.navigateTo({
	      url: '/pages/index/add-account'
	    });
	  }
    },
  mounted() {
    this.fetchMonthlyData();
  }
};
</script>

<style scoped>
.financial-report {
  font-family: Arial, sans-serif;
  padding: 20px;
}

.date-selector {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 20px;
}

.year-selector, .month-selector {
  display: flex;
  align-items: center;
  margin: 0 10px;
}

.year-selector label, .month-selector label {
  margin-right: 10px;
}

.year-selector select, .month-selector select {
  padding: 5px;
}

</style>