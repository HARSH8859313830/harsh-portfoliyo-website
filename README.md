# harsh-portfoliyo-website
import React from "react";
import { motion } from "framer-motion";
import { Github, Linkedin, Mail, Globe, Play, ExternalLink, Code2, Sparkles, FileText } from "lucide-react";

const portfolioData = {
  name: "Harsh Sharma",
  title: "AI Enthusiast & Automation Builder | Python Developer",
  tagline: "Young innovator building AI-powered tools and automations to solve real-world problems — from dashboards to social media managers and beyond.",
  location: "Hathras, Uttar Pradesh, India",
  email: "hs7251316@gmail.com",
  headlineCTAs: [
    { label: "Download Resume", icon: FileText, href: "#resume", variant: "primary" },
    { label: "View Projects", icon: Play, href: "#projects", variant: "secondary" }
  ],
  socials: [
    { label: "GitHub", icon: Github, href: "https://github.com/yourhandle" },
    { label: "LinkedIn", icon: Linkedin, href: "https://www.linkedin.com/in/harsh-sharma-27639a365" },
    { label: "Portfolio", icon: Globe, href: "#home" },
    { label: "Email", icon: Mail, href: "mailto:hs7251316@gmail.com" }
  ],
  skills: [
    "Python",
    "Flask",
    "Unity",
    "Generative AI",
    "Microsoft Excel",
    "Automation",
    "OpenAI API",
    "Data Analytics",
    "Cybersecurity Basics",
    "Editing"
  ],
  featuredMetrics: [
    { value: "6+", label: "AI Projects", sub: "prototyped & tested" },
    { value: "4", label: "Certifications", sub: "in AI & Tech" },
    { value: "2024–2025", label: "Learning Phase", sub: "Hands-on exploration" }
  ],
  experience: [
    {
      org: "Personal & Academic Projects",
      role: "AI & Automation Builder",
      period: "2024 – Present",
      bullets: [
        "Developed a social media automation tool to reduce content turnaround by 70%.",
        "Created Python + Excel analytics dashboards for smarter data handling.",
        "Experimented with Unity + AI integrations to gamify learning."
      ]
    }
  ],
  education: [
    {
      school: "ABS Inter College Mahavatpur",
      period: "Apr 2025 – Apr 2026",
      detail: "High School Student | Excel & Python Enthusiast | Generative AI Learner"
    }
  ],
  projects: [
    {
      name: "AI Social Media Post Generator",
      desc: "An automation tool that creates captions, hashtags, and visuals for creators and NGOs.",
      tags: ["Python", "OpenAI API", "Automation"],
      links: [{ label: "GitHub", href: "https://github.com/yourhandle/social-post-gen", external: true }],
      impact: "Cut down manual content creation effort by 70%."
    },
    {
      name: "Analytics Dashboard",
      desc: "Python + Excel-based dashboard with AI integration for dataset insights and visualization.",
      tags: ["Python", "Excel", "Analytics"],
      links: [{ label: "Demo", href: "#", external: true }],
      impact: "Improved efficiency in analyzing reports by 50%."
    },
    {
      name: "Unity AI Learning Game",
      desc: "Gamified educational project combining Unity with AI-powered interactions.",
      tags: ["Unity", "AI", "Gamification"],
      links: [{ label: "Case Study", href: "#", external: true }],
      impact: "Enhanced peer engagement in learning AI basics."
    }
  ],
  certifications: [
    { title: "Deloitte Australia - Data Analytics Job Simulation", year: "2025", org: "Deloitte" },
    { title: "Deloitte Australia - Cybersecurity Job Simulation", year: "2025", org: "Deloitte" },
    { title: "Deloitte Australia - Technology Job Simulation", year: "2025", org: "Deloitte" },
    { title: "2-Day AI Master Workshop", year: "2025", org: "Outskill" }
  ],
  testimonials: [
    {
      quote: "Harsh is a motivated and quick-learning AI enthusiast who transforms ideas into practical, working tools.",
      author: "Mentor, AI Workshop"
    }
  ]
};

const Section = ({ id, title, children }) => (
  <section id={id} className="w-full max-w-5xl mx-auto px-4 py-8">
    {title && (
      <div className="flex items-center gap-3 mb-4">
        <Sparkles className="w-5 h-5 text-gray-600" />
        <h2 className="text-2xl font-semibold">{title}</h2>
      </div>
    )}
    {children}
  </section>
);

export default function PortfolioSimple() {
  return (
    <div className="min-h-screen bg-gray-50 text-gray-900">
      <header className="bg-white shadow-sm sticky top-0 z-40">
        <div className="max-w-5xl mx-auto px-4 py-3 flex items-center justify-between">
          <a href="#home" className="font-bold">{portfolioData.name}.ai</a>
          <nav className="hidden md:flex items-center gap-4 text-sm text-gray-700">
            <a href="#projects" className="hover:underline">Projects</a>
            <a href="#skills" className="hover:underline">Skills</a>
            <a href="#experience" className="hover:underline">Experience</a>
            <a href="#contact" className="hover:underline">Contact</a>
            <a href="#resume" className="ml-3 inline-flex items-center gap-2 border px-3 py-1 rounded-md text-sm">
              <FileText className="w-4 h-4" /> Resume
            </a>
          </nav>
        </div>
      </header>

      <main>
        <section id="home" className="max-w-5xl mx-auto px-4 py-12 grid md:grid-cols-2 gap-8 items-center">
          <div>
            <h1 className="text-3xl md:text-4xl font-bold">{portfolioData.title}</h1>
            <p className="mt-4 text-gray-600">{portfolioData.tagline}</p>
            <div className="mt-6 flex flex-wrap gap-3">
              {portfolioData.headlineCTAs.map((cta, i) => (
                <a key={i} href={cta.href} className={`inline-flex items-center gap-2 px-4 py-2 rounded-md border ${cta.variant === "primary" ? "bg-black text-white" : "bg-white text-black"}`}>
                  <cta.icon className="w-4 h-4" /> {cta.label}
                </a>
              ))}
            </div>
            <div className="mt-6 flex flex-wrap gap-4 text-sm">
              {portfolioData.socials.map((s, i) => (
                <a key={i} href={s.href} target="_blank" rel="noreferrer" className="inline-flex items-center gap-2 opacity-90 hover:opacity-100">
                  <s.icon className="w-4 h-4" /> {s.label}
                </a>
              ))}
            </div>
            <div className="mt-6 grid grid-cols-3 gap-3">
              {portfolioData.featuredMetrics.map((m, i) => (
                <div key={i} className="rounded-lg border p-3 bg-white">
                  <div className="text-xl font-semibold">{m.value}</div>
                  <div className="text-sm">{m.label}</div>
                  <div className="text-xs text-gray-500">{m.sub}</div>
                </div>
              ))}
            </div>
          </div>
          <div>
            <motion.div initial={{ opacity: 0, scale: 0.98 }} animate={{ opacity: 1, scale: 1 }} transition={{ duration: 0.5 }} className="rounded-xl border p-6 bg-white">
              <div className="flex items-center gap-2 text-sm text-gray-500 mb-3">
                <Code2 className="w-4 h-4" /> Live Preview
              </div>
              <div className="rounded-lg bg-gray-50 p-4 text-sm">
                <div className="mb-2 font-medium">Automation Pipeline</div>
                <ul className="list-disc pl-5 space-y-1 text-gray-600">
                  <li>Idea → Prompt → Draft</li>
                  <li>Review → Edit → Approve</li>
                  <li>Publish → Analyze → Improve</li>
                </ul>
                <a href="#projects" className="mt-4 inline-flex items-center gap-2 text-sm">See how I build this <ExternalLink className="w-4 h-4" /></a>
              </div>
            </motion.div>
          </div>
        </section>

        <Section id="projects" title="Projects">
          <div className="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
            {portfolioData.projects.map((p, i) => (
              <article key={i} className="rounded-xl border bg-white p-4">
                <h3 className="font-medium text-lg">{p.name}</h3>
                <p className="text-sm text-gray-600 mt-2">{p.desc}</p>
                <div className="flex flex-wrap gap-2 mt-3 text-xs">
                  {p.tags.map((t, ti) => (
                    <span key={ti} className="px-2 py-1 rounded bg-gray-100">{t}</span>
                  ))}
                </div>
                <div className="text-xs text-gray-500 mt-2">Impact: {p.impact}</div>
                <div className="flex gap-3 mt-3">
                  {p.links.map((l, li) => (
                    <a key={li} href={l.href} target={l.external ? "_blank" : undefined} rel="noreferrer" className="text-sm inline-flex items-center gap-2">{l.label} <ExternalLink className="w-3 h-3" /></a>
                  ))}
                </div>
              </article>
            ))}
          </div>
        </Section>

        <Section id="skills" title="Skills">
          <div className="grid grid-cols-2 md:grid-cols-4 gap-3">
            {portfolioData.skills.map((s, i) => (
              <div key={i} className="rounded-lg border bg-white p-3 text-sm flex items-center justify-between"><span>{s}</span><span className="text-xs text-gray-500">Pro</span></div>
            ))}
          </div>
        </Section>

        <Section id="experience" title="Experience">
          <div className="space-y-4">
            {portfolioData.experience.map((e, i) => (
              <div key={i} className="rounded-lg border bg-white p-4">
                <div className="flex items-center justify-between">
                  <div><div className="font-medium">{e.role}</div><div className="text-sm text-gray-600">{e.org}</div></div>
                  <div className="text-sm text-gray-500">{e.period}</div>
                </div>
                <ul className="list-disc pl-5 mt-3 text-sm text-gray-600">{e.bullets.map((b, bi) => (<li key={bi}>{b}</li>))}</ul>
              </div>
            ))}
          </div>
        </Section>

        <Section id="education" title="Education">
          <div className="grid gap-4">
            {portfolioData.education.map((ed, i) => (
              <div key={i} className="rounded-lg border bg-white p-4">
                <div className="flex items-center justify-between"><div><div className="font-medium">{ed.school}</div><div className="text-sm text-gray-600">{ed.detail}</div></div><div className="text-sm text-gray-500">{ed.period}</div></div>
              </div>
            ))}
          </div>
        </Section>

        <Section id="certifications" title="Certifications">
          <div className="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">{portfolioData.certifications.map((c, i) => (<div key={i} className="rounded-lg border bg-white p-4"><div className="font-medium">{c.title}</div><div className="text-sm text-gray-600">{c.org} • {c.year}</div></div>))}</div>
        </Section>

        <Section id="testimonials" title="Testimonials">
          <div className="grid md:grid-cols-2 gap-4">{portfolioData.testimonials.map((t, i) => (<div key={i} className="rounded-lg border bg-white p-6"><p className="text-sm">“{t.quote}”</p><div className="mt-3 text-xs text-gray-500">— {t.author}</div></div>))}</div>
        </Section>

        <Section id="contact" title="Contact">
          <div className="grid md:grid-cols-2 gap-8">
            <div>
              <p className="text-gray-600 text-sm mb-4">Interested in collaborating or hiring me for AI automation work? Drop a note.</p>
              <div className="space-y-2 text-sm"><div className="flex items-center gap-2"><Mail className="w-4 h-4" /> {portfolioData.email}</div><div className="flex items-center gap-2"><Linkedin className="w-4 h-4" /> LinkedIn DMs preferred</div></div>
            </div>
            <form onSubmit={(e) => e.preventDefault()} className="space-y-3">
              <div className="grid grid-cols-2 gap-3"><input className="border rounded px-3 py-2" placeholder="Your name" required /><input className="border rounded px-3 py-2" type="email" placeholder="Your email" required /></div>
              <input className="border rounded px-3 py-2" placeholder="Subject" required />
              <textarea className="border rounded p-3" placeholder="Your message" rows={5} required />
              <button type="submit" className="inline-flex items-center gap-2 px-4 py-2 rounded-md bg-black text-white">Send Message</button>
            </form>
          </div>
        </Section>

        <section id="resume" className="max-w-5xl mx-auto px-4 py-12">
          <h2 className="text-2xl font-semibold mb-4">Resume</h2>
          <div className="rounded-lg border bg-white p-4 text-sm"><p className="font-medium">Contact</p><p className="text-gray-600">{portfolioData.email}</p><div className="mt-3"><p className="font-medium">Summary</p><p className="text-gray-600">I am an AI enthusiast and automation builder with hands-on experience building mini tools and dashboards using Python, Excel and generative AI. Actively seeking remote internship or part-time roles to grow practical experience.</p></div></div>
        </section>
      </main>

      <footer className="border-t mt-12 bg-white">
        <div className="max-w-5xl mx-auto px-4 py-6 text-xs text-gray-600 flex items-center justify-between"><div>© {new Date().getFullYear()} {portfolioData.name}. All rights reserved.</div><div className="flex items-center gap-4"><a href="#home" className="hover:underline">Back to top</a></div></div>
      </footer>
    </div>
  );
}
