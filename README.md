Applications on Voice Blast - https://www.youtube.com/watch?v=McBvE0ryxH4&t=9s



# VoiceBlast
Complete Cloud-Based Voice Broadcasting Solution - No Infrastructure Required! 🎯  VoiceBlast is a fully managed cloud telephony API that lets you integrate professional automated calling campaigns into your applications without owning any servers, Asterisk PBX, or telecom infrastructure. Just call our API and start broadcasting! By Sharan Khanna
# 🚀 VoiceBlast - Cloud-Based Auto Dialer API

[![License: Commercial](https://img.shields.io/badge/License-Commercial-red.svg)]()
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Status: Production Ready](https://img.shields.io/badge/Status-Production%20Ready-brightgreen.svg)]()

> **Complete Cloud-Based Voice Broadcasting Solution - No Infrastructure Required!** 🎯

VoiceBlast is a **fully managed cloud telephony API** that lets you integrate professional automated calling campaigns into your applications **without owning any servers, Asterisk PBX, or telecom infrastructure**. Just call our API and start broadcasting!

**Built by**: Sharan Khanna, Founder [IndiaTransform.com](https://IndiaTransform.com) Contact +91 9643644684

---

## 🌟 What Makes VoiceBlast Different?

### ✅ **Zero Infrastructure Needed**
- No Asterisk server setup required
- No SIP trunk management
- No server maintenance
- No telephony expertise needed

### ✅ **We Provide Everything**
- **Hosted Asterisk PBX** - Enterprise-grade calling infrastructure
- **Cloud TTS Engine** - Natural Hindi & English voice synthesis
- **SIP Connectivity** - Pre-configured telecom routes
- **24/7 Uptime** - Managed infrastructure with monitoring

### ✅ **Simple REST API**
- Create campaigns in seconds
- Real-time call status tracking
- Automatic DTMF detection & call transfer
- Built-in approval workflow

### ✅ **Pay-As-You-Go**
- Coin-based pricing system
- No monthly fees
- No setup costs
- Only pay for campaigns you run

---

## 💰 What You're Actually Leasing

When you use VoiceBlast API, you get access to:

1. **Hosted Asterisk PBX Server** (Fully configured & maintained)
2. **Cloud TTS Server** (Hindi voice synthesis)
3. **SIP Trunk/GSM Gateway** (For actual call connectivity)
4. **API Backend** (Campaign management & monitoring)
5. **Storage Infrastructure** (Audio files & call records)

**You focus on your app. We handle the telecom infrastructure.**

---

## 🎯 Perfect For

### 🏢 **SaaS Developers**
Build voice broadcasting features into your CRM, ERP, or business software without telecom headaches.

### 📱 **App Developers**
Add automated calling to mobile apps - perfect for reminders, notifications, and marketing.

### 🎪 **Digital Agencies**
Offer voice campaign services to clients without infrastructure investment.

### 🏦 **Startups**
Launch MVP with calling features in days, not months.

### 📊 **Marketing Platforms**
Integrate multi-channel campaigns (Email + SMS + Voice) seamlessly.

---

## 🚀 Getting Started (It's Really Simple!)

### Step 1: Get API Access
```bash
# Contact for API credentials
WhatsApp: +91 9643644684
Email: sharan4khanna@gmail.com
```

### Step 2: Load Coins
```python
import requests

API_BASE = "https://api.voiceblast.cloud/api"  # Your hosted endpoint

# Add coins to your account
response = requests.post(f"{API_BASE}/coins/add", json={
    "user_id": "your_user_id",
    "amount": 100  # Buy 100 campaign credits
})
```

### Step 3: Create Your First Campaign
```python
# Create a campaign with Hindi message
response = requests.post(f"{API_BASE}/campaign/create", json={
    "user_id": "your_user_id",
    "main_message": "नमस्ते! यह एक परीक्षण संदेश है। धन्यवाद!",
    "contacts": [
        {
            "name": "राजेश कुमार",
            "number": "919999999999",
            "company": "ABC कंपनी"
        },
        {
            "name": "प्रिया शर्मा", 
            "number": "919888888888",
            "company": "XYZ Ltd"
        }
    ]
})

campaign_id = response.json()['campaign_id']
print(f"Campaign created: {campaign_id}")
```

### Step 4: Approve & Launch
```python
# Approve campaign (deducts 1 coin)
response = requests.post(f"{API_BASE}/campaign/{campaign_id}/approve")

print(response.json())
# Output: {
#   "status": "approved_and_running",
#   "coins_deducted": 1,
#   "remaining_coins": 99
# }
```

### Step 5: Monitor Progress
```python
# Check campaign status in real-time
response = requests.get(f"{API_BASE}/campaign/{campaign_id}/status")

stats = response.json()
print(f"Total: {stats['stats']['total']}")
print(f"Success: {stats['stats']['success']}")
print(f"Transferred: {stats['stats']['transferred']}")
```

**That's it! Calls are being made from our cloud infrastructure.**

---

## 📡 Complete API Reference

### 🏥 Health Check
```http
GET /api/health
```

**Response:**
```json
{
  "status": "ok",
  "service": "VoiceBlast AutoDialer API",
  "timestamp": "2025-01-15T10:30:00"
}
```

---

### 💰 Coin Management

#### Check Balance
```http
POST /api/coins/balance
Content-Type: application/json

{
  "user_id": "your_user_id"
}
```

**Response:**
```json
{
  "user_id": "your_user_id",
  "balance": 50
}
```

#### Add Coins
```http
POST /api/coins/add
Content-Type: application/json

{
  "user_id": "your_user_id",
  "amount": 100
}
```

---

### 📞 Campaign Management

#### Create Bulk Campaign
```http
POST /api/campaign/create
Content-Type: application/json

{
  "user_id": "your_user_id",
  "main_message": "आपका ऑर्डर तैयार है। कृपया स्टोर से संग्रह करें।",
  "contacts": [
    {
      "name": "Customer Name",
      "number": "919999999999",
      "company": "Your Business"
    }
  ]
}
```

**Response:**
```json
{
  "campaign_id": "550e8400-e29b-41d4-a716-446655440000",
  "status": "pending_approval",
  "contacts_count": 100,
  "message": "Campaign created. Awaiting approval..."
}
```

#### Single Call API
```http
POST /api/call/single
Content-Type: application/json

{
  "user_id": "your_user_id",
  "number": "919999999999",
  "name": "राज कुमार",
  "company": "ABC Ltd",
  "main_message": "आपकी अपॉइंटमेंट कल सुबह 10 बजे है।"
}
```

#### Approve Campaign
```http
POST /api/campaign/{campaign_id}/approve
```

**Note:** Deducts 1 coin and starts the campaign immediately.

#### Reject Campaign
```http
POST /api/campaign/{campaign_id}/reject
```

**Note:** No coins deducted. Campaign is cancelled.

#### Get Campaign Status
```http
GET /api/campaign/{campaign_id}/status
```

**Response:**
```json
{
  "campaign_id": "550e8400-e29b-41d4-a716-446655440000",
  "created_at": "2025-01-15T10:30:00",
  "contacts_count": 100,
  "approved": true,
  "stats": {
    "total": 100,
    "success": 87,
    "failed": 8,
    "transferred": 15,
    "status": "completed"
  },
  "active_calls": 5
}
```

#### List All Campaigns
```http
GET /api/campaigns
```

#### List Pending Approvals
```http
GET /api/pending_approvals
```

---

## 🎤 How The Call Flow Works

Our infrastructure handles everything automatically:

1. **Call Initiation** - We dial the number from our Asterisk server
2. **Personalized Greeting** - TTS generates: *"नमस्ते {name} जी, मैं {company} से बोल रहा हूँ।"*
3. **Main Message** - Your custom message plays
4. **Interactive Prompt** - *"अधिक जानकारी के लिए 1 दबाएं।"*
5. **DTMF Detection** - We listen for digit presses
6. **Live Transfer** - When user presses "1", call transfers to your team
7. **Analytics** - Full stats available via API

**All audio generation, call routing, and DTMF handling happens on our servers!**

---

## 💡 Real-World Use Cases

### 📚 EdTech Platform
```python
# Send exam reminders to 10,000 students
contacts = load_students_from_db()  # Your database
response = requests.post(f"{API_BASE}/campaign/create", json={
    "user_id": "edtech_platform",
    "main_message": "आपकी परीक्षा 25 जनवरी को है। कृपया एडमिट कार्ड डाउनलोड करें।",
    "contacts": contacts
})
```

### 🏥 Healthcare App
```python
# Appointment reminders
response = requests.post(f"{API_BASE}/call/single", json={
    "user_id": "hospital_app",
    "number": "919999999999",
    "name": "मरीज़",
    "company": "सिटी हॉस्पिटल",
    "main_message": "आपकी अपॉइंटमेंट कल दोपहर 2 बजे है। डॉ. शर्मा के साथ।"
})
```

### 🛒 E-commerce
```python
# Order ready notifications
for order in pending_orders:
    requests.post(f"{API_BASE}/call/single", json={
        "user_id": "ecommerce_store",
        "number": order['phone'],
        "name": order['customer_name'],
        "company": "ShopKart",
        "main_message": f"आपका ऑर्डर {order['id']} तैयार है। कृपया स्टोर से लें।"
    })
```

### 🗳️ Political Campaign
```python
# Voter outreach
response = requests.post(f"{API_BASE}/campaign/create", json={
    "user_id": "political_party",
    "main_message": "नमस्ते! मैं XYZ पार्टी से बोल रहा हूँ। कृपया 5 फरवरी को वोट जरूर दें।",
    "contacts": voter_list  # 50,000 voters
})
```

---

## 📊 Pricing & Billing

### Coin System
- **1 Coin = 1 Campaign** (unlimited contacts in that campaign)
- Coins are deducted only when campaign is approved
- Failed campaigns don't consume coins
- No expiry on purchased coins

### Cost Structure
| Package | Coins | Price | Per Campaign |
|---------|-------|-------|--------------|
| Starter | 10 | Contact Us | Contact Us |
| Growth | 50 | Contact Us | Contact Us |
| Business | 200 | Contact Us | Contact Us |
| Enterprise | Custom | Custom | Custom |

**📞 Contact: +91 9643644684 (WhatsApp) for pricing**

---

## 🔒 Security & Compliance

- ✅ User-based authentication
- ✅ Campaign approval workflow
- ✅ Audit logs for all operations
- ✅ NDNC (Do Not Call) compliance ready
- ✅ Data encryption in transit
- ✅ Secure coin transaction system

---

## 🛠️ Technical Architecture

```
┌─────────────────┐
│   Your App      │
│  (Any Platform) │
└────────┬────────┘
         │ HTTPS
         ▼
┌─────────────────────────────────────┐
│    VoiceBlast Cloud (We Manage)     │
├─────────────────────────────────────┤
│  ┌──────────────┐  ┌─────────────┐ │
│  │  API Server  │  │ TTS Engine  │ │
│  │  (Flask)     │  │  (Hindi)    │ │
│  └──────┬───────┘  └──────┬──────┘ │
│         │                  │        │
│  ┌──────▼──────────────────▼──────┐ │
│  │   Asterisk PBX Server          │ │
│  │   - AMI Interface              │ │
│  │   - Call Routing               │ │
│  │   - DTMF Detection             │ │
│  └──────┬─────────────────────────┘ │
│         │                            │
│  ┌──────▼─────────┐                 │
│  │  SIP Trunk     │                 │
│  │  GSM Gateway   │                 │
│  └────────────────┘                 │
└─────────────────────────────────────┘
         │
         ▼
   📞 Phone Network
```

**You only interact with the API. Everything else is handled by our infrastructure.**

---

## 🚀 Why Lease Our Infrastructure?

### ❌ Without VoiceBlast (Traditional Way):
- Buy/rent servers (₹5,000-20,000/month)
- Install & configure Asterisk (weeks of work)
- Purchase SIP trunk (₹10,000+ setup)
- Hire telecom expert (₹50,000+/month)
- Maintain 24/7 uptime
- Handle scaling issues
- **Total: ₹100,000+ first month, ongoing costs**

### ✅ With VoiceBlast:
- Make API call
- **Start in 5 minutes**
- **Pay only for campaigns**
- **Total: From as low as ₹0 setup cost**

---

## 📞 Getting Started

### Step 1: Contact Us
**WhatsApp/Call:** +91 9643644684  
**Founder:** Sharan Khanna  
**Company:** IndiaTransform.com

### Step 2: Get Credentials
We'll provide:
- Your unique `user_id`
- API endpoint URL
- Initial coin balance (trial)

### Step 3: Integrate
Use any programming language that supports HTTP:
- Python
- Node.js
- PHP
- Java
- Go
- Ruby
- .NET

### Step 4: Go Live!
Start making calls within minutes.

---

## 📚 Code Examples

### Python
```python
import requests

class VoiceBlastClient:
    def __init__(self, user_id, api_base):
        self.user_id = user_id
        self.api_base = api_base
    
    def create_campaign(self, message, contacts):
        response = requests.post(f"{self.api_base}/campaign/create", json={
            "user_id": self.user_id,
            "main_message": message,
            "contacts": contacts
        })
        return response.json()
    
    def approve_campaign(self, campaign_id):
        response = requests.post(f"{self.api_base}/campaign/{campaign_id}/approve")
        return response.json()

# Usage
client = VoiceBlastClient("your_user_id", "https://api.voiceblast.cloud/api")
result = client.create_campaign(
    "परीक्षा की तैयारी शुरू करें!",
    [{"name": "Student", "number": "919999999999", "company": "School"}]
)
```

### Node.js
```javascript
const axios = require('axios');

class VoiceBlastClient {
  constructor(userId, apiBase) {
    this.userId = userId;
    this.apiBase = apiBase;
  }

  async createCampaign(message, contacts) {
    const response = await axios.post(`${this.apiBase}/campaign/create`, {
      user_id: this.userId,
      main_message: message,
      contacts: contacts
    });
    return response.data;
  }
}

// Usage
const client = new VoiceBlastClient('your_user_id', 'https://api.voiceblast.cloud/api');
```

### PHP
```php
<?php
class VoiceBlastClient {
    private $userId;
    private $apiBase;
    
    public function __construct($userId, $apiBase) {
        $this->userId = $userId;
        $this->apiBase = $apiBase;
    }
    
    public function createCampaign($message, $contacts) {
        $data = [
            'user_id' => $this->userId,
            'main_message' => $message,
            'contacts' => $contacts
        ];
        
        $ch = curl_init($this->apiBase . '/campaign/create');
        curl_setopt($ch, CURLOPT_POST, 1);
        curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($data));
        curl_setopt($ch, CURLOPT_HTTPHEADER, ['Content-Type: application/json']);
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
        
        return json_decode(curl_exec($ch), true);
    }
}
?>
```

---

## 🎯 Features Breakdown

### ✨ What's Included

| Feature | Description | Your Benefit |
|---------|-------------|--------------|
| **Hindi TTS** | Natural-sounding Hindi voice | No voice recording needed |
| **Personalization** | Name & company in greeting | Higher engagement |
| **DTMF Detection** | Automatic key press capture | Interactive campaigns |
| **Call Transfer** | Live routing to your team | Convert interested leads |
| **Real-time Stats** | Success/failure tracking | Monitor ROI instantly |
| **Approval Workflow** | Review before launch | Prevent mistakes |
| **Coin System** | Fair usage billing | Pay for what you use |
| **8-second Stagger** | Prevents network overload | Higher success rate |

---

## 🆘 Support & Custom Development

### Need Help?
- **WhatsApp Support:** +91 9643644684
- **Email:** contact@indiatransform.com
- **Response Time:** Within 24 hours

### Custom Features
We can develop:
- Custom TTS voices
- Regional language support (Tamil, Telugu, Bengali, etc.)
- Advanced call routing logic
- CRM integrations
- Webhook notifications
- Custom reporting dashboards
- White-label solutions

**Contact us for custom quotes!**

---

## 📄 License & Terms

- Commercial API - Not open source
- Usage subject to fair use policy
- Compliance with Indian telecom regulations required
- NDNC (National Do Not Call Registry) compliance is user's responsibility

---

## 🌟 Success Stories

> *"Integrated VoiceBlast in our school management system. Now we send exam reminders to 5,000 parents in minutes!"*  
> — **EdTech Startup, Bangalore**

> *"Our e-commerce app now sends order confirmations via voice. Reduced customer queries by 40%!"*  
> — **Online Retailer, Delhi**

> *"Perfect for our political campaign. Reached 50,000 voters in one day without any infrastructure!"*  
> — **Campaign Manager, Mumbai**

---

## 🚀 Ready to Start?

### Contact Now:
📱 **WhatsApp/Call:** +91 9643644684  
👤 **Founder:** Sharan Khanna  
🌐 **Website:** [IndiaTransform.com](https://IndiaTransform.com)  
✉️ **Email:** sharan4khanna@gmail.com

**Available 24/7 for custom requests and urgent support!**

---

## ⚡ Quick Facts

- ✅ No infrastructure investment required
- ✅ Start in 5 minutes
- ✅ Simple REST API
- ✅ Hindi TTS included
- ✅ Pay per campaign
- ✅ Real-time monitoring
- ✅ 24/7 uptime guaranteed
- ✅ Managed by telecom experts

---

**Made with ❤️ in India by Sharan Khanna | IndiaTransform.com**

*Empowering businesses with cloud telephony since 2008*
