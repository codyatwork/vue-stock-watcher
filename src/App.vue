<template>
  <h1 class="heading">Stock Watcher</h1>
  <form class="add-input-group" @submit.prevent="addStock">
    <input
      class="add-input"
      type="text"
      placeholder="Enter stock symbol"
      :value="input"
      @input="input = $event.target.value.toUpperCase()"
    />
    <button class="add-button">
      Add<span class="verbose-button-text"> Stock</span>
    </button>
  </form>
  <p v-if="error === errors.duplicate" class="error-message">
    This stock is already on your dashboard.
  </p>
  <p v-else-if="error === errors.notFound" class="error-message">
    Stock not found (they're hardcoded -
    <a
      href="https://github.com/codyatwork/vue-stock-watcher#the-stocks-are-hard-coded-here-are-the-ones-included"
      target="_blank"
      rel="noopener"
    >
      see the available stocks here</a
    >).
  </p>
  <div class="stocks">
    <StockCard
      v-for="stock in stocks"
      :key="stock.symbol"
      class="stock"
      v-bind="stock"
    />
  </div>
</template>

<script>
import StockCard from "./components/StockCard.vue";

const availableStocks = {
  GOOG: {
    high: 709.28,
    low: 689.47,
    name: "Alphabet Inc. CL C",
    open: 691,
    price: 706.32,
    symbol: "GOOG",
  },
  YHOO: {
    high: 29.66,
    low: 29.06,
    name: "Yahoo! Inc",
    open: 29.28,
    price: 29.27,
    symbol: "YHOO",
  },
  AIG: {
    high: 53.47,
    low: 52.28,
    name: "American International Group Inc",
    open: 52.06,
    price: 53.08,
    symbol: "AIG",
  },
  UWTIF: {
    high: 1.74,
    low: 1.5,
    name: "VelocityShares 3x Long Crude ETN",
    open: 1.37,
    price: 1.61,
    symbol: "UWTIF",
  },
  DWTIF: {
    high: 297.5,
    low: 245.59,
    name: "3x Inverse Crude",
    open: 307.1,
    price: 253.41,
    symbol: "DWTIF",
  },
  GRPN: {
    high: 4.13,
    low: 3.6,
    name: "Groupon Inc",
    open: 4.08,
    price: 3.74,
    symbol: "GRPN",
  },
};

export default {
  name: "App",
  components: {
    StockCard,
  },
  data() {
    return {
      error: null,
      errors: { duplicate: "duplicate", notFound: "notFound" },
      input: "",
      stocks: [],
    };
  },
  methods: {
    addStock() {
      if (availableStocks[this.input]) {
        if (this.stocks.some((stock) => stock.symbol === this.input)) {
          this.error = this.errors.duplicate;
        } else {
          this.stocks.push(availableStocks[this.input]);
          this.error = null;
          this.input = "";
        }
      } else {
        this.error = this.errors.notFound;
      }
    },
  },
};
</script>

<style>
@import "./assets/base.css";

#app {
  margin: auto;
  max-width: 1250px;
  padding: 0 0.75rem;
}

@media (prefers-color-scheme: dark) {
  #app {
    color: var(--background);
  }
}

@media screen and (min-width: 768px) {
  #app {
    padding: 2rem;
  }
}
</style>

<style scoped>
.heading {
  font-weight: 600;
  margin: revert;
}

.add-input-group {
  display: flex;
  height: 50px;
  margin-bottom: 1rem;
}

.add-input {
  background: inherit;
  border: 1px solid #e1e2e4;
  flex: 1;
  font-family: inherit;
  font-size: 16px;
  padding: 1rem;
}

.add-button {
  background: var(--button);
  color: white;
  border: 0;
  box-shadow: 0px 14px 33px -18px var(--button);
  cursor: pointer;
  font-family: inherit;
  font-weight: 800;
  margin-left: 0.5rem;
  padding: 0 1.4rem;
  text-transform: uppercase;
  white-space: nowrap;
}

.verbose-button-text {
  display: none;
  font-weight: inherit;
}

.error-message {
  color: var(--red);
  margin: revert;
}

.stocks {
  grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
  grid-gap: 1rem;
}

.stock {
  margin-bottom: 0.5rem;
}

@media (prefers-color-scheme: dark) {
  .add-input {
    color: var(--background);
  }

  .add-input::placeholder {
    color: #b7c3ca;
  }

  .error-message {
    color: var(--red-light);
  }
}

@media screen and (min-width: 768px) {
  .heading {
    font-size: 60px;
  }

  .add-input-group {
    margin-bottom: 2rem;
    width: 27rem;
  }

  .add-button {
    padding: 0 2rem;
  }

  .verbose-button-text {
    display: unset;
  }

  .stocks {
    display: grid;
  }

  .stock {
    margin: 0;
  }
}
</style>
