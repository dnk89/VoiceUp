# VoiceUp — EdTech SaaS Platform

**VoiceUp** is a specialized educational platform designed for the rehabilitation and learning of children and adults with speech and hearing impairments. It also provides critical support for students in multilingual environments (e.g., helping refugee or other children adapt to the national educational system).

---

## 🎯 Mission & Vision

To provide equal access to quality education by combining modern speech therapy and deaf education methods with the power of Artificial Intelligence to overcome both linguistic and physical barriers.

---

* ## 🏗 Architecture: Modular Monolith
The project follows a **Modular Monolith** approach, emphasizing clean boundaries and high performance without the complexity of third-party service buses.

* **Loosely Coupled:** Each module (Identity, Catalog, Speech, Localization) is logically isolated with its own data schema.
* **Native Messaging:** We use built-in .NET features like `System.Threading.Channels` and custom event dispatchers to maintain module isolation without external library overhead.
* **Scalability-ready:** The architecture is designed so that any high-load module (e.g., Speech Processing) can be extracted into a standalone microservice with minimal effort.
---

## 🛠 Tech Stack

* **Runtime:** `.NET 10` (C# 14)
* **Database:** `PostgreSQL` (utilizing separate schemas per module)
* **ORM:** `Entity Framework Core`
* **Communication:** Native .NET Dependency Injection and internal Async Streams for inter-module events.
* **AI/ML:** Integration with `Azure Speech Services` and `DeepL API/OpenAI` for speech analysis and real-time translation.
* **Observability:** `OpenTelemetry`, `Serilog`.

---

## 📂 Project Structure

```text
/src
  ├── /Host            # Entry point (ASP.NET Core Web API Host)
  ├── /Modules         # Business Modules
  │    ├── /Identity   # Authentication & Profile Management (RBAC)
  │    ├── /Catalog    # Educational content & Media library
  │    ├── /Speech     # Audio processing & AI-driven speech analysis
  │    └── /Localization # Translations & Content adaptation
  └── /Shared          # Common infrastructure, Contracts, and BuildingBlocks

```

---

## 🚀 Key Features (Roadmap)

* [ ] **Core Architecture:** Modular Monolith skeleton and module registration system.
* [ ] **Bilingual Support:** Multi-language content storage (Latvian/Ukrainian/Russian) with dynamic switching.
* [ ] **Speech Analysis:** Real-time sound wave visualization and AI-powered pronunciation checking.
* [ ] **Real-time Translation:** Synchronous subtitling for live lessons to support hearing-impaired students.
* [ ] **Parent/Teacher Dashboard:** Tracking rehabilitation progress and educational milestones.

---

## ⚙️ Getting Started

1. Clone the repository:
```bash
git clone https://github.com/your-username/VoiceUp.git

```


2. Ensure you have the **.NET 10 SDK** installed.
3. Open the project in Visual Studio, Rider, VS Code using the `VoiceUp.slnx` file, or run via CLI:
```bash
dotnet run --project src/Host/VoiceUp.Web

```



---

## 🛡 Security & Accessibility

* **WCAG 2.1 Compliance:** Interface designed for users with hearing impairments (visual cues instead of audio-only alerts).
* **Data Protection:** Adhering to **GDPR** standards, ensuring anonymization for children's profiles.
