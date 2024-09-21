

# 📈 Real-time Stock Price Application with Fluvio 🚀

Welcome to the **Real-time Stock Price Application**! This project leverages **Fluvio** for streaming real-time stock prices, combined with a **Next.js** frontend that visualizes the data using **Recharts**. 📊✨

## 🛠️ Prerequisites

Before you begin, ensure you have the following installed:

1. ### **Fluvio CLI** 🖥️
   - **Install Fluvio**:
     ```bash
     curl -fsS https://packages.fluvio.io/v1/install.sh | bash
     ```
   - **Add Fluvio to your shell**:
     ```bash
     source ~/.bashrc # or ~/.zshrc depending on your shell
     ```
   - **Verify the installation**:
     ```bash
     fluvio version
     ```

2. ### **Fluvio Cluster** ☁️
   - **Set up a local Fluvio cluster**:
     ```bash
     fluvio cluster start
     ```
   - Alternatively, you can use **Fluvio Cloud** for a managed cluster.

3. ### **Node.js** 🟢
   - **Ensure you have Node.js installed** (v16.x or later).
   - **Download Node.js** from [here](https://nodejs.org).

4. ### **Docker** 🐳
   - **Install Docker** from [here](https://docs.docker.com/get-docker/).

---

## 🚀 Setting Up the Project

### 1. 🏷️ Fluvio Topic Creation

Create a Fluvio topic to handle real-time stock data:

```bash
fluvio topic create stock-data
```

This topic will be used to stream real-time stock prices to the frontend.

### 2. 🖥️ Setting Up the Backend (Server)

The backend simulates or receives stock price data and streams it to the frontend via **Fluvio**.

1. **Create an `index.js` file** for your server:

   *(Content as provided earlier)*

2. **Install the dependencies**:

   ```bash
   npm install express @fluvio/client
   ```

3. **Start the server**:

   ```bash
   node index.js
   ```

### 3. 🌐 Setting Up the Frontend (Next.js App)

#### 📦 Install Next.js and Other Dependencies

1. **Create a new Next.js project** (if not already):

   ```bash
   npx create-next-app stock-prices-app
   ```

2. **Navigate to the project folder**:

   ```bash
   cd stock-prices-app
   ```

3. **Install the required dependencies**:

   ```bash
   npm install recharts moment
   ```

#### 🛠️ Add Stock Chart and Stock Switch Components

- **Create a new file `components/StockChart.js`** for displaying stock prices:

  *(Content as provided earlier with emoticons)*

- **Create a `components/StockSwitch.js`** to allow switching between different stocks:

  *(Content as provided earlier with emoticons)*

#### 📝 Update the `pages/index.js` to Integrate Components

- **Modify the `pages/index.js` file** to use `StockChart` and `StockSwitch`:

  *(Content as provided earlier with emoticons)*

---

## 🛠️ Deployment Automation

To streamline the deployment process, use the provided **Bash script**. Here's how to integrate and use it:

### 1. **Add the Deployment Script**

- **Location**: Place the script in the `scripts/` directory of your project.

  ```
  stock-prices-app/
  ├── components/
  ├── pages/
  ├── scripts/
  │   └── deploy.sh
  ├── ...
  ```

- **Make Executable**:

  ```bash
  chmod +x scripts/deploy.sh
  ```

### 2. **Usage Instructions**

Add a section in your **README** detailing how to use the deployment script.

#### 🖥️ Running the Deployment Script

1. **Navigate to the Project Root**:

   ```bash
   cd stock-prices-app
   ```

2. **Execute the Deployment Script**:

   ```bash
   ./scripts/deploy.sh [PACKAGE_VERSION] [HTTP_SOURCES_DIR]
   ```

   - **Parameters**:
     - `PACKAGE_VERSION` (optional): Version of the package to deploy (default: `0.3.8`).
     - `HTTP_SOURCES_DIR` (optional): Directory containing `.yml` configuration files (default: current directory `.`).

   - **Example**:

     ```bash
     ./scripts/deploy.sh 0.3.8 ./configurations
     ```

 
