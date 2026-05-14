scentverse-platform/
│
├── client/
│   ├── public/
│   ├── src/
│   │   ├── app/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── context/
│   │   ├── styles/
│   │   └── utils/
│
├── server/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── middleware/
│   ├── config/
│   └── server.js
│
├── package.json
└── README.mdnpx create-next-app@latest client✔ TypeScript: Yes
✔ Tailwind: Yes
✔ App Router: Yes
✔ ESLint: Yesclient/src/app/page.tsx'use client'

import { motion } from 'framer-motion'

export default function Home() {
  return (
    <main className="bg-black text-white min-h-screen">

      <section className="h-screen flex flex-col justify-center items-center text-center px-6">
        <motion.h1
          initial={{ opacity: 0, y: 40 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 1 }}
          className="text-6xl font-bold"
        >
          SCENTVERSE
        </motion.h1>

        <motion.p
          initial={{ opacity: 0 }}
          animate={{ opacity: 1 }}
          transition={{ delay: 0.5 }}
          className="mt-6 text-xl text-gray-300 max-w-2xl"
        >
          Luxury perfumes powered by connected marketing.
          Earn commissions. Build teams. Grow wealth.
        </motion.p>

        <button className="mt-10 px-8 py-4 rounded-2xl bg-purple-600 hover:bg-purple-700 transition text-lg font-semibold">
          Join The Movement
        </button>
      </section>

      <section className="py-24 px-6 bg-zinc-900">
        <div className="max-w-6xl mx-auto grid md:grid-cols-3 gap-10">

          <div className="bg-zinc-800 p-8 rounded-3xl">
            <h2 className="text-2xl font-bold mb-4">Sell Perfumes</h2>
            <p>
              Start earning by selling premium fragrances online.
            </p>
          </div>

          <div className="bg-zinc-800 p-8 rounded-3xl">
            <h2 className="text-2xl font-bold mb-4">Build Teams</h2>
            <p>
              Invite others and earn referral commissions.
            </p>
          </div>

          <div className="bg-zinc-800 p-8 rounded-3xl">
            <h2 className="text-2xl font-bold mb-4">Track Earnings</h2>
            <p>
              Use your dashboard to monitor profits and performance.
            </p>
          </div>

        </div>
      </section>

    </main>
  )
}npm install firebaseclient/src/firebase.tsimport { initializeApp } from 'firebase/app'
import { getAuth } from 'firebase/auth'

const firebaseConfig = {
  apiKey: process.env.NEXT_PUBLIC_FIREBASE_API_KEY,
  authDomain: process.env.NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN,
  projectId: process.env.NEXT_PUBLIC_FIREBASE_PROJECT_ID,
  storageBucket: process.env.NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET,
  messagingSenderId: process.env.NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID,
  appId: process.env.NEXT_PUBLIC_FIREBASE_APP_ID,
}

const app = initializeApp(firebaseConfig)

export const auth = getAuth(app)server/models/User.jsconst mongoose = require('mongoose')

const userSchema = new mongoose.Schema({
  name: String,
  email: String,
  password: String,

  referralCode: String,
  referredBy: String,

  walletBalance: {
    type: Number,
    default: 0
  },

  totalSales: {
    type: Number,
    default: 0
  },

  commissions: {
    type: Number,
    default: 0
  },

  role: {
    type: String,
    default: 'user'
  }
})

module.exports = mongoose.model('User', userSchema)const mongoose = require('mongoose')

const productSchema = new mongoose.Schema({
  name: String,
  description: String,
  image: String,
  price: Number,
  stock: Number,
  category: String
})

module.exports = mongoose.model('Product', productSchema)const mongoose = require('mongoose')

const orderSchema = new mongoose.Schema({
  userId: String,
  products: Array,
  totalAmount: Number,
  status: {
    type: String,
    default: 'Pending'
  }
})

module.exports = mongoose.model('Order', orderSchema)const referralBonus = order.totalAmount * 0.1

referrer.walletBalance += referralBonus
referrer.commissions += referralBonusclient/src/app/dashboard/page.tsxexport default function Dashboard() {
  return (
    <div className="min-h-screen bg-black text-white p-8">
      <h1 className="text-4xl font-bold mb-10">Dashboard</h1>

      <div className="grid md:grid-cols-3 gap-8">

        <div className="bg-zinc-900 p-6 rounded-3xl">
          <h2 className="text-xl">Wallet</h2>
          <p className="text-3xl font-bold mt-4">UGX 0</p>
        </div>

        <div className="bg-zinc-900 p-6 rounded-3xl">
          <h2 className="text-xl">Sales</h2>
          <p className="text-3xl font-bold mt-4">0</p>
        </div>

        <div className="bg-zinc-900 p-6 rounded-3xl">
          <h2 className="text-xl">Referrals</h2>
          <p className="text-3xl font-bold mt-4">0</p>
        </div>

      </div>
    </div>
  )
}npm install whatsapp-web.jsconst { Client } = require('whatsapp-web.js')

const client = new Client()

client.on('ready', () => {
  console.log('WhatsApp Connected')
})

client.initialize()npm install flutterwave-node-v3git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin mainAdd New SiteImport From GitHubNew Web ServiceNEXT_PUBLIC_FIREBASE_API_KEY=
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=
NEXT_PUBLIC_FIREBASE_PROJECT_ID=MONGO_URI=
JWT_SECRET=
CLOUDINARY_API_KEY=
FLUTTERWAVE_SECRET_KEY=cd client
npm install
npm run devcd server
npm install
node server.js# Essence-
