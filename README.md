# Danieeb-Danieeb
import { useState, useEffect, useRef } from "react";

const certs = [
  { name: "Introduction to Python", date: "Sep 23, 2025", hrs: 4, icon: "🐍", color: "#F7C948", id: "#43,267,799" },
  { name: "Intermediate Python", date: "Sep 29, 2025", hrs: 4, icon: "🐍", color: "#F7C948", id: "#43,290,644" },
  { name: "AI Ethics", date: "Oct 25, 2025", hrs: 1, icon: "🤖", color: "#a78bfa", id: "#43,964,369" },
  { name: "Data Manipulation with pandas", date: "Nov 25, 2025", hrs: 4, icon: "🐼", color: "#34d399", id: "#43,562,981" },
  { name: "Introduction to Power BI", date: "Apr 29, 2026", hrs: 4, icon: "📊", color: "#F2C811", id: "#47,460,440" },
  { name: "Introduction to Git", date: "May 01, 2026", hrs: 2, icon: "🌿", color: "#f97316", id: "#47,482,085" },
  { name: "Introduction to SQL", date: "May 03, 2026", hrs: 2, icon: "🗄️", color: "#60a5fa", id: "#47,558,258" },
];

const totalHrs = certs.reduce((s, c) => s + c.hrs, 0);

const skills = [
  { name: "Python", color: "#F7C948", icon: "🐍" },
  { name: "pandas", color: "#34d399", icon: "🐼" },
  { name: "SQL", color: "#60a5fa", icon: "🗄️" },
  { name: "Power BI", color: "#F2C811", icon: "📊" },
  { name: "Git", color: "#f97316", icon: "🌿" },
  { name: "AI Ethics", color: "#a78bfa", icon: "🤖" },
];

const TypeWriter = ({ words }) => {
  const [index, setIndex] = useState(0);
  const [subIndex, setSubIndex] = useState(0);
  const [deleting, setDeleting] = useState(false);
  const [text, setText] = useState("");
  useEffect(() => {
    if (subIndex === words[index].length + 1 && !deleting) { setTimeout(() => setDeleting(true), 1600); return; }
    if (subIndex === 0 && deleting) { setDeleting(false); setIndex(p => (p + 1) % words.length); return; }
    const t = setTimeout(() => { setText(words[index].substring(0, subIndex)); setSubIndex(p => p + (deleting ? -1 : 1)); }, deleting ? 55 : 95);
    return () => clearTimeout(t);
  }, [subIndex, index, deleting, words]);
  return <span style={{ color: "#34d399" }}>{text}<span style={{ animation: "blink 1s step-end infinite" }}>|</span></span>;
};

// Progress bar for learning journey
const Timeline = () => (
  <div style={{ position: "relative", paddingLeft: "20px" }}>
    <div style={{ position: "absolute", left: "7px", top: 0, bottom: 0, width: "2px", background: "linear-gradient(to bottom, #34d399, #60a5fa, #a78bfa)" }} />
    {certs.map((c, i) => (
      <div key={i} style={{ display: "flex", alignItems: "flex-start", marginBottom: i < certs.length - 1 ? "16px" : 0, position: "relative" }}>
        <div style={{
          position: "absolute", left: "-16px", top: "4px",
          width: "10px", height: "10px", borderRadius: "50%",
          background: c.color, boxShadow: `0 0 8px ${c.color}88`,
          flexShrink: 0,
        }} />
        <div style={{ flex: 1 }}>
          <div style={{ display: "flex", justifyContent: "space-between", alignItems: "center" }}>
            <span style={{ fontSize: "13px", fontWeight: 600, color: "#e6edf3" }}>
              {c.icon} {c.name}
            </span>
            <span style={{ fontSize: "11px", color: "#8b949e", marginLeft: "12px", whiteSpace: "nowrap" }}>{c.hrs}h · {c.date}</span>
          </div>
          <div style={{ fontSize: "11px", color: "#6e7681", marginTop: "2px" }}>DataCamp {c.id}</div>
        </div>
      </div>
    ))}
  </div>
);

export default function DanielProfile() {
  const [copied, setCopied] = useState(false);
  const [activeTab, setActiveTab] = useState("preview");

  const markdown = `<!-- Daniel Emad — GitHub Profile README -->
<!-- Replace YOUR_USERNAME with your actual GitHub username -->

<div align="center">

# Hi, I'm **Daniel Emad** 👋

### Aspiring Data Analyst · Python Learner · Always Curious 📈

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/YOUR_PROFILE)
[![DataCamp](https://img.shields.io/badge/DataCamp-03EF62?style=for-the-badge&logo=datacamp&logoColor=black)](https://datacamp.com/profile/YOUR_USERNAME)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your@email.com)

</div>

---

## 🧑‍💻 About Me

- 📊 Passionate about **data, analytics, and turning numbers into stories**
- 🌱 Currently building my foundation: Python → pandas → SQL → Power BI
- 🤖 Thinking about the ethical side of AI — not just the technical side
- 🚀 More certifications coming **very soon** — stay tuned!
- ⚡ Fun fact: I completed 21 hours of DataCamp courses in just a few months

---

## 🛠️ Skills & Tools

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

---

## 🏅 DataCamp Certifications (21 hrs total)

| Course | Hours | Completed |
|--------|-------|-----------|
| 🐍 Introduction to Python | 4 hrs | Sep 23, 2025 |
| 🐍 Intermediate Python | 4 hrs | Sep 29, 2025 |
| 🤖 AI Ethics | 1 hr | Oct 25, 2025 |
| 🐼 Data Manipulation with pandas | 4 hrs | Nov 25, 2025 |
| 📊 Introduction to Power BI | 4 hrs | Apr 29, 2026 |
| 🌿 Introduction to Git | 2 hrs | May 01, 2026 |
| 🗄️ Introduction to SQL | 2 hrs | May 03, 2026 |

> 🔥 More coming soon...

---

## 📊 GitHub Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=YOUR_USERNAME&show_icons=true&theme=tokyonight&hide_border=true" height="160"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_USERNAME&layout=compact&theme=tokyonight&hide_border=true" height="160"/>
</p>

---

<div align="center">

*"Data is the new oil — I'm here to refine it."*

![Profile Views](https://komarev.com/ghpvc/?username=YOUR_USERNAME&color=03EF62&style=flat-square)

</div>`;

  const handleCopy = () => {
    navigator.clipboard.writeText(markdown);
    setCopied(true);
    setTimeout(() => setCopied(false), 2500);
  };

  return (
    <div style={{ minHeight: "100vh", background: "#0d1117", color: "#e6edf3", fontFamily: "'Segoe UI', system-ui, sans-serif" }}>
      <style>{`
        @keyframes blink { 50% { opacity: 0 } }
        @keyframes fadeUp { from { opacity:0; transform:translateY(16px) } to { opacity:1; transform:translateY(0) } }
        @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.4} }
        @keyframes glow { 0%,100%{box-shadow:0 0 8px #34d39944} 50%{box-shadow:0 0 20px #34d39988} }
        .card { animation: fadeUp 0.5s ease both; }
        .skill-pill:hover { transform: scale(1.06); filter: brightness(1.2); }
        .cert-row:hover { background: #1c2128 !important; }
        .tab:hover { color: #e6edf3 !important; }
        .copy-btn:hover { background: #34d399 !important; color: #0d1117 !important; }
      `}</style>

      {/* Top Banner */}
      <div style={{
        background: "linear-gradient(160deg, #0d1117 0%, #111827 40%, #0d1117 100%)",
        borderBottom: "1px solid #21262d",
        padding: "44px 24px 36px",
        textAlign: "center",
        position: "relative",
        overflow: "hidden",
      }}>
        {/* Floating dots */}
        {[...Array(8)].map((_, i) => (
          <div key={i} style={{
            position: "absolute",
            width: `${[2,3,4,2,3,4,2,3][i]}px`, height: `${[2,3,4,2,3,4,2,3][i]}px`,
            borderRadius: "50%", background: ["#34d399","#60a5fa","#a78bfa","#F7C948","#f97316","#34d399","#60a5fa","#a78bfa"][i],
            opacity: 0.4,
            top: `${[15,65,30,80,20,55,75,10][i]}%`,
            left: `${[5,8,88,92,80,3,85,18][i]}%`,
            animation: `pulse ${2 + i * 0.4}s ease-in-out infinite`,
          }} />
        ))}

        {/* Avatar */}
        <div style={{
          width: "90px", height: "90px", borderRadius: "50%",
          background: "linear-gradient(135deg, #34d399 0%, #60a5fa 50%, #a78bfa 100%)",
          margin: "0 auto 16px",
          display: "flex", alignItems: "center", justifyContent: "center",
          fontSize: "38px",
          animation: "glow 3s ease-in-out infinite",
        }}>📊</div>

        <h1 style={{ margin: "0 0 6px", fontSize: "30px", fontWeight: 700, letterSpacing: "-0.5px" }}>
          Daniel Emad
        </h1>
        <div style={{ fontSize: "15px", color: "#8b949e", marginBottom: "18px" }}>
          <TypeWriter words={["Aspiring Data Analyst 📈", "Python Developer 🐍", "Lifelong Learner 🎓", "Always Curious 🔍"]} />
        </div>

        {/* Badges */}
        <div style={{ display: "flex", gap: "8px", justifyContent: "center", flexWrap: "wrap" }}>
          {[
            { l: "LinkedIn", c: "#0A66C2", bg: "#1a2f3e" },
            { l: "DataCamp", c: "#03EF62", bg: "#0a1f0f" },
            { l: "Email", c: "#f85149", bg: "#3d1f1f" },
          ].map(b => (
            <span key={b.l} style={{
              padding: "5px 16px", borderRadius: "20px",
              background: b.bg, color: b.c,
              fontSize: "12px", fontWeight: 600,
              border: `1px solid ${b.c}40`, cursor: "pointer",
            }}>{b.l}</span>
          ))}
        </div>
      </div>

      <div style={{ maxWidth: "740px", margin: "0 auto", padding: "28px 20px" }}>

        {/* Quick Stats Row */}
        <div className="card" style={{ display: "grid", gridTemplateColumns: "repeat(3,1fr)", gap: "12px", marginBottom: "24px", animationDelay: "0.05s" }}>
          {[
            { v: "7", l: "Certificates", icon: "🏅", c: "#F7C948" },
            { v: `${totalHrs}h`, l: "Learning Hours", icon: "⏱️", c: "#34d399" },
            { v: "2026", l: "Active Since", icon: "📅", c: "#60a5fa" },
          ].map((s, i) => (
            <div key={i} style={{
              background: "#161b22", borderRadius: "12px",
              border: `1px solid ${s.c}22`, padding: "16px 12px", textAlign: "center",
            }}>
              <div style={{ fontSize: "20px", marginBottom: "4px" }}>{s.icon}</div>
              <div style={{ fontSize: "22px", fontWeight: 700, color: s.c }}>{s.v}</div>
              <div style={{ fontSize: "11px", color: "#8b949e" }}>{s.l}</div>
            </div>
          ))}
        </div>

        {/* About */}
        <div className="card" style={{ animationDelay: "0.1s", marginBottom: "22px" }}>
          <h2 style={{ fontSize: "16px", fontWeight: 600, marginBottom: "12px", display: "flex", alignItems: "center", gap: "8px" }}>
            🧑‍💻 About Me
          </h2>
          <div style={{ background: "#161b22", borderRadius: "12px", border: "1px solid #21262d", padding: "18px", borderLeft: "3px solid #34d399" }}>
            {[
              { icon: "📊", text: <>Passionate about <strong style={{color:"#34d399"}}>data, analytics & turning numbers into stories</strong></> },
              { icon: "🌱", text: "Building my stack step by step: Python → pandas → SQL → Power BI" },
              { icon: "🤖", text: "Thinking about the ethical side of AI — not just the technical part" },
              { icon: "🚀", text: <><strong style={{color:"#f97316"}}>More certifications coming very soon</strong> — stay tuned!</> },
              { icon: "⚡", text: "Fun fact: 21 hours of DataCamp courses completed in just a few months 🔥" },
            ].map((item, i) => (
              <div key={i} style={{ display: "flex", gap: "10px", marginBottom: i < 4 ? "9px" : 0, fontSize: "13px", lineHeight: "1.6" }}>
                <span>{item.icon}</span>
                <span style={{ color: "#c9d1d9" }}>{item.text}</span>
              </div>
            ))}
          </div>
        </div>

        {/* Skills */}
        <div className="card" style={{ animationDelay: "0.15s", marginBottom: "22px" }}>
          <h2 style={{ fontSize: "16px", fontWeight: 600, marginBottom: "12px" }}>🛠️ Skills & Tools</h2>
          <div style={{ display: "flex", gap: "10px", flexWrap: "wrap" }}>
            {skills.map((s, i) => (
              <div className="skill-pill" key={i} style={{
                background: `${s.color}18`, border: `1px solid ${s.color}50`,
                borderRadius: "10px", padding: "9px 16px",
                display: "flex", alignItems: "center", gap: "7px",
                fontSize: "13px", fontWeight: 600, color: s.color,
                cursor: "default", transition: "all 0.2s",
              }}>
                {s.icon} {s.name}
              </div>
            ))}
          </div>
        </div>

        {/* Certificates Timeline */}
        <div className="card" style={{ animationDelay: "0.2s", marginBottom: "22px" }}>
          <h2 style={{ fontSize: "16px", fontWeight: 600, marginBottom: "12px", display: "flex", alignItems: "center", gap: "8px" }}>
            🏅 DataCamp Journey
            <span style={{ fontSize: "12px", background: "#34d39920", color: "#34d399", border: "1px solid #34d39940", padding: "2px 10px", borderRadius: "20px" }}>
              {totalHrs} hrs · 7 certs
            </span>
          </h2>
          <div style={{ background: "#161b22", borderRadius: "12px", border: "1px solid #21262d", padding: "20px 20px 20px 28px" }}>
            <Timeline />
            {/* "More coming soon" */}
            <div style={{ display: "flex", alignItems: "center", gap: "10px", marginTop: "16px", paddingLeft: "4px" }}>
              <div style={{ width: "10px", height: "10px", borderRadius: "50%", border: "2px dashed #6e7681", animation: "pulse 2s infinite", flexShrink: 0, marginLeft: "-20px" }} />
              <span style={{ fontSize: "12px", color: "#6e7681", fontStyle: "italic" }}>🔥 More coming soon...</span>
            </div>
          </div>
        </div>

        {/* Progress visual */}
        <div className="card" style={{ animationDelay: "0.25s", marginBottom: "22px" }}>
          <h2 style={{ fontSize: "16px", fontWeight: 600, marginBottom: "12px" }}>📈 Learning Progress</h2>
          <div style={{ background: "#161b22", borderRadius: "12px", border: "1px solid #21262d", padding: "18px" }}>
            {[
              { skill: "Python", pct: 85, color: "#F7C948" },
              { skill: "pandas", pct: 70, color: "#34d399" },
              { skill: "SQL", pct: 50, color: "#60a5fa" },
              { skill: "Power BI", pct: 60, color: "#F2C811" },
              { skill: "Git", pct: 55, color: "#f97316" },
            ].map((p, i) => (
              <div key={i} style={{ marginBottom: i < 4 ? "12px" : 0 }}>
                <div style={{ display: "flex", justifyContent: "space-between", marginBottom: "5px" }}>
                  <span style={{ fontSize: "12px", color: "#c9d1d9" }}>{p.skill}</span>
                  <span style={{ fontSize: "11px", color: "#6e7681" }}>{p.pct}%</span>
                </div>
                <div style={{ background: "#21262d", borderRadius: "4px", height: "6px" }}>
                  <div style={{
                    width: `${p.pct}%`, height: "100%", borderRadius: "4px",
                    background: `linear-gradient(90deg, ${p.color}aa, ${p.color})`,
                    transition: "width 1s ease",
                  }} />
                </div>
              </div>
            ))}
          </div>
        </div>

        {/* Quote */}
        <div className="card" style={{ animationDelay: "0.3s", marginBottom: "28px" }}>
          <div style={{
            background: "linear-gradient(135deg, #161b22, #0d1117)",
            borderRadius: "12px", border: "1px solid #21262d",
            padding: "22px", textAlign: "center",
            borderLeft: "4px solid #34d399",
          }}>
            <div style={{ fontSize: "14px", color: "#8b949e", fontStyle: "italic" }}>
              "Data is the new oil — I'm here to refine it."
            </div>
          </div>
        </div>

        {/* Copy button */}
        <div style={{ textAlign: "center" }}>
          <button className="copy-btn" onClick={handleCopy} style={{
            background: copied ? "#34d399" : "#21262d",
            color: copied ? "#0d1117" : "#e6edf3",
            border: "1px solid #30363d",
            borderRadius: "10px", padding: "13px 36px",
            fontSize: "15px", fontWeight: 600, cursor: "pointer",
            transition: "all 0.2s",
          }}>
            {copied ? "✅ Copied! Paste into your README.md" : "📋 Copy My README Markdown"}
          </button>
          <div style={{ color: "#6e7681", fontSize: "12px", marginTop: "10px" }}>
            Create a repo named <code style={{color:"#34d399"}}>danielemad/danielemad</code> and paste as README.md
          </div>
        </div>

      </div>
    </div>
  );
}
