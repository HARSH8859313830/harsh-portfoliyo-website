# harsh-portfoliyo-website                                                                          
import React from "react";
import { motion } from "framer-motion";
import {
  Github,
  Linkedin,
  Mail,
  Globe,
  Play,
  ArrowRight,
  ExternalLink,
  Code2,
  FileText,
  Zap,
} from "lucide-react";

// --- Data Structure (Unchanged) ---

const portfolioData = {
  name: "Harsh Sharma",
  title: "AI Enthusiast & Automation Builder | Python Developer",
  tagline:
    "Young innovator building AI-powered tools and automations to solve real-world problems — from dashboards to social media managers and beyond.",
  location: "Hathras, Uttar Pradesh, India",
  email: "hs7251316@gmail.com",
  phone: "",
  headlineCTAs: [
    { label: "View Resume Summary", icon: FileText, href: "#resume", variant: "primary" }, // Changed label for clarity
    { label: "View Projects", icon: Play, href: "#projects", variant: "secondary" },
  ],
  socials: [
    { label: "GitHub", icon: Github, href: "https://github.com/yourhandle" },
    { label: "LinkedIn", icon: Linkedin, href: "https://www.linkedin.com/in/harsh-sharma-27639a365" },
    { label: "Portfolio", icon: Globe, href: "#home" },
    { label: "Email", icon: Mail, href: "mailto:hs7251316@gmail.com" },
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
    "Editing",
  ],
  featuredMetrics: [
    { value: "6+", label: "AI Projects", sub: "prototyped & tested" },
    { value: "4", label: "Certifications", sub: "in AI & Tech" },
    { value: "2024–2025", label: "Learning Phase", sub: "Hands-on exploration" },
  ],
  experience: [
    {
      org: "Personal & Academic Projects",
      role: "AI & Automation Builder",
      period: "2024 – Present",
      bullets: [
        "Developed a social media automation tool to reduce content turnaround by 70%.",
        "Created Python + Excel analytics dashboards for smarter data handling.",
        "Experimented with Unity + AI integrations to gamify learning.",
      ],
    },
  ],
  education: [
    {
      school: "ABS Inter College Mahavatpur",
      period: "Apr 2025 – Apr 2026",
      detail: "High School Student | Excel & Python Enthusiast | Generative AI Learner",
    },
  ],
  projects: [
    {
      name: "AI Social Media Post Generator",
      desc: "An automation tool that creates captions, hashtags, and visuals for creators and NGOs.",
      tags: ["Python", "OpenAI API", "Automation"],
      links: [
        { label: "GitHub", href: "https://github.com/yourhandle/social-post-gen", external: true },
      ],
      impact: "Cut down manual content creation effort by 70%.",
    },
    {
      name: "Analytics Dashboard",
      desc: "Python + Excel-based dashboard with AI integration for dataset insights and visualization.",
      tags: ["Python", "Excel", "Analytics"],
      links: [{ label: "Demo", href: "#", external: true }],
      impact: "Improved efficiency in analyzing reports by 50%.",
    },
    {
      name: "Unity AI Learning Game",
      desc: "Gamified educational project combining Unity with AI-powered interactions.",
      tags: ["Unity", "AI", "Gamification"],
      links: [{ label: "Case Study", href: "#", external: true }],
      impact: "Enhanced peer engagement in learning AI basics.",
    },
  ],
  certifications: [
    { title: "Deloitte Australia - Data Analytics Job Simulation", year: "2025", org: "Deloitte" },
    { title: "Deloitte Australia - Cybersecurity Job Simulation", year: "2025", org: "Deloitte" },
    { title: "Deloitte Australia - Technology Job Simulation", year: "2025", org: "Deloitte" },
    { title: "2-Day AI Master Workshop", year: "2025", org: "Outskill" },
  ],
  testimonials: [
    {
      quote:
        "Harsh is a motivated and quick-learning AI enthusiast who transforms ideas into practical, working tools.",
      author: "Mentor, AI Workshop",
    },
  ],
};

// --- Framer Motion Variants (Optimized for Speed) ---

const itemVariants = {
  hidden: { opacity: 0, y: 10 },
  visible: {
    opacity: 1,
    y: 0,
    // Shorter duration for a snappier feel
    transition: { type: "spring", stiffness: 150, damping: 18, duration: 0.4 },
  },
};

const containerVariants = {
  hidden: { opacity: 0 },
  visible: {
    opacity: 1,
    transition: {
      // Reduced stagger for faster sequence
      staggerChildren: 0.05,
    },
  },
};

// --- Reusable Section Component (with Quick Entrance Animation) ---

const Section = ({ id, title, children }) => (
  <motion.section
    id={id}
    className="w-full max-w-5xl mx-auto px-4 py-12"
    variants={containerVariants}
    initial="hidden"
    whileInView="visible"
    // Triggers quickly (when 10% of the section is visible)
    viewport={{ once: true, amount: 0.1 }}
  >
    {title && (
      <motion.div variants={itemVariants} className="flex items-center gap-3 mb-8 text-indigo-200">
        <Zap className="w-6 h-6 text-cyan-400" />
        <h2 className="text-3xl font-bold border-b-2 border-cyan-400 pb-1">{title}</h2>
      </motion.div>
    )}
    {children}
  </motion.section>
);

// --- Main Portfolio Component ---

export default function PortfolioSimple() {
  const CTAButton = ({ cta }) => (
    <motion.a
      href={cta.href}
      className={`inline-flex items-center gap-2 px-5 py-2.5 rounded-full font-semibold transition-all duration-300 shadow-lg`}
      // Snappier hover effect
      whileHover={{ scale: 1.05, boxShadow: "0 6px 12px rgba(0, 255, 255, 0.2)" }}
      whileTap={{ scale: 0.98 }}
      style={{
        backgroundColor: cta.variant === 'primary' ? '#00FFFF' : 'rgba(0, 0, 0, 0.7)',
        color: cta.variant === 'primary' ? '#000000' : '#FFFFFF',
        border: cta.variant === 'secondary' ? '1px solid #00FFFF' : 'none',
      }}
    >
      <cta.icon className="w-5 h-5" /> {cta.label}
    </motion.a>
  );

  const MetricCard = ({ m }) => (
    <motion.div 
      className="rounded-xl border border-indigo-700 p-4 bg-indigo-900/50 backdrop-blur-sm text-center"
      variants={itemVariants}
      whileHover={{ scale: 1.03, borderColor: '#00FFFF' }} // Reduced scale for speed
      transition={{ duration: 0.15 }}
    >
      <div className="text-3xl font-extrabold text-cyan-400">{m.value}</div>
      <div className="text-sm font-medium text-white">{m.label}</div>
      <div className="text-xs text-indigo-400 mt-1">{m.sub}</div>
    </motion.div>
  );

  /**
   * FIX: Removed the redundant 'i' prop which was only used for an internal key,
   * relying solely on the key provided by the parent map for stability.
   */
  const ProjectCard = ({ p }) => ( 
    <motion.article 
      className="rounded-xl border border-indigo-700 bg-indigo-900/40 p-5 text-white shadow-xl hover:shadow-cyan-400/20 transition-all duration-150"
      variants={itemVariants}
      whileHover={{ y: -3, boxShadow: "0 8px 15px rgba(0, 255, 255, 0.1)" }}
    >
      <h3 className="font-semibold text-xl text-cyan-300">{p.name}</h3>
      <p className="text-sm text-indigo-300 mt-3 line-clamp-2">{p.desc}</p>
      <div className="flex flex-wrap gap-2 mt-4 text-xs">
        {p.tags.map((t, ti) => (
          <span key={ti} className="px-3 py-1 rounded-full bg-indigo-700 text-indigo-100 font-medium">{t}</span>
        ))}
      </div>
      <div className="text-xs text-cyan-500 mt-3 font-mono">⚡ Impact: {p.impact}</div>
      <div className="flex gap-4 mt-4">
        {p.links.map((l, li) => (
          <motion.a 
            key={li} 
            href={l.href} 
            target={l.external ? "_blank" : undefined} 
            rel={l.external ? "noopener noreferrer" : undefined} // BUG FIX: Added rel for security
            className="text-sm inline-flex items-center gap-2 text-cyan-400 hover:text-white"
            whileHover={{ x: 2 }}
          >
            {l.label} <ExternalLink className="w-3 h-3" />
          </motion.a>
        ))}
      </div>
    </motion.article>
  );


  return (
    // Vibrant background gradient for a cool look
    <div className="min-h-screen bg-gray-900 text-white font-sans" 
          style={{ background: 'linear-gradient(135deg, #0f172a 0%, #1e3a8a 100%)' }}>
      
      {/* Header/Nav */}
      <header className="sticky top-0 z-40 backdrop-blur-md bg-gray-900/70 shadow-lg border-b border-indigo-700">
        <div className="max-w-5xl mx-auto px-4 py-4 flex items-center justify-between">
          <a href="#home" className="font-extrabold text-xl text-cyan-400">{portfolioData.name}.ai</a>
          <nav className="hidden md:flex items-center gap-6 text-sm">
            {['projects', 'skills', 'experience', 'certifications', 'contact'].map(id => (
                <a key={id} href={`#${id}`} className="text-indigo-200 hover:text-cyan-400 transition-colors capitalize">{id}</a>
            ))}
            <CTAButton cta={portfolioData.headlineCTAs[0]} />
          </nav>
        </div>
      </header>

      <main>
        {/* HERO SECTION (HOME) */}
        <section id="home" className="max-w-5xl mx-auto px-4 py-20 grid md:grid-cols-2 gap-12 items-center">
          <div>
            <motion.h1 
              initial={{ opacity: 0, y: -30 }} 
              animate={{ opacity: 1, y: 0 }} 
              transition={{ duration: 0.5 }} // Faster
              className="text-4xl md:text-6xl font-extrabold text-white leading-tight"
            >
              {portfolioData.title}
            </motion.h1>
            <motion.p 
              initial={{ opacity: 0 }} 
              animate={{ opacity: 1 }} 
              transition={{ duration: 0.7, delay: 0.1 }} // Faster
              className="mt-4 text-indigo-200 text-lg"
            >
              {portfolioData.tagline}
            </motion.p>

            {/* CTAs */}
            <motion.div 
              initial="hidden" 
              animate="visible" 
              variants={containerVariants}
              className="mt-8 flex flex-wrap gap-4"
            >
              {portfolioData.headlineCTAs.map((cta, i) => (
                <motion.div key={i} variants={itemVariants}>
                    <CTAButton cta={cta} />
                </motion.div>
              ))}
            </motion.div>

            {/* Socials */}
            <div className="mt-8 flex flex-wrap gap-6 text-sm">
              {portfolioData.socials.map((s, i) => (
                <motion.a 
                  key={i} 
                  href={s.href} 
                  target="_blank" 
                  rel="noopener noreferrer" // BUG FIX: Added rel for security
                  className="inline-flex items-center gap-2 text-indigo-300 hover:text-cyan-400 transition-colors"
                  whileHover={{ scale: 1.05 }} // Snappier
                >
                  <s.icon className="w-5 h-5" /> {s.label}
                </motion.a>
              ))}
            </div>

            {/* Featured Metrics */}
            <motion.div 
              initial="hidden" 
              animate="visible" 
              variants={containerVariants}
              className="mt-10 grid grid-cols-3 gap-4"
            >
              {portfolioData.featuredMetrics.map((m, i) => (
                <MetricCard key={i} m={m} />
              ))}
            </motion.div>
          </div>

          {/* Side Info Card (Animated) */}
          <motion.div 
            initial={{ opacity: 0, x: 30 }} 
            animate={{ opacity: 1, x: 0 }} 
            transition={{ duration: 0.5, delay: 0.2 }} // Faster
            className="rounded-xl border border-cyan-400 p-8 bg-gray-800/60 shadow-2xl shadow-cyan-500/10"
          >
            <div className="flex items-center gap-3 text-lg text-cyan-400 mb-4 font-semibold">
              <Code2 className="w-5 h-5" /> Automation Pipeline
            </div>
            <div className="rounded-lg bg-indigo-900/50 p-5 text-sm">
              <div className="mb-3 font-bold text-white">The Build Cycle</div>
              <ul className="list-disc pl-5 space-y-2 text-indigo-200">
                <li>Idea → Prompt → **Draft** (AI Generation)</li>
                <li>Review → Edit → **Approve** (Human Oversight)</li>
                <li>Publish → Analyze → **Improve** (Iteration)</li>
              </ul>
              <a href="#projects" className="mt-5 inline-flex items-center gap-2 text-sm text-cyan-400 hover:text-white transition-colors">
                See real projects <ArrowRight className="w-4 h-4" />
              </a>
            </div>
          </motion.div>
        </section>

        {/* PROJECTS SECTION */}
        <Section id="projects" title="Projects">
          <div className="grid sm:grid-cols-2 lg:grid-cols-3 gap-8">
            {/* FIX: Removed i prop from ProjectCard call */}
            {portfolioData.projects.map((p, i) => (
              <ProjectCard key={i} p={p} /> 
            ))}
          </div>
        </Section>

        {/* SKILLS SECTION */}
        <Section id="skills" title="Skills & Tech Stack">
          <motion.div 
            className="grid grid-cols-2 md:grid-cols-4 gap-4"
            variants={containerVariants}
          >
            {portfolioData.skills.map((s, i) => (
              <motion.div 
                key={i} 
                className="rounded-xl border border-indigo-700 bg-indigo-900/50 p-4 text-sm flex items-center justify-between text-white"
                variants={itemVariants}
                whileHover={{ backgroundColor: '#00FFFF', color: '#000000', borderColor: '#00FFFF' }}
                transition={{ duration: 0.1 }} // Very fast transition
              >
                <span>{s}</span>
                <span className="text-xs text-cyan-400 font-bold">PRO</span>
              </motion.div>
            ))}
          </motion.div>
        </Section>

        {/* EXPERIENCE SECTION */}
        <Section id="experience" title="Experience">
          <div className="space-y-6">
            {portfolioData.experience.map((e, i) => (
              <motion.div 
                key={i} 
                className="rounded-xl border border-indigo-700 bg-gray-800/50 p-6 text-white"
                variants={itemVariants}
              >
                <div className="flex items-start justify-between">
                  <div>
                    <div className="font-bold text-xl text-cyan-300">{e.role}</div>
                    <div className="text-md text-indigo-300 mt-1">{e.org}</div>
                  </div>
                  <div className="text-sm text-indigo-400 font-mono pt-1">{e.period}</div>
                </div>
                <ul className="list-disc pl-5 mt-4 text-sm text-indigo-200 space-y-2">
                  {e.bullets.map((b, bi) => (
                    <li key={bi}>{b}</li>
                  ))}
                </ul>
              </motion.div>
            ))}
          </div>
        </Section>

        {/* EDUCATION SECTION */}
        <Section id="education" title="Education">
          <div className="grid gap-4">
            {portfolioData.education.map((ed, i) => (
              <motion.div 
                key={i} 
                className="rounded-lg border border-indigo-700 bg-gray-800/50 p-4"
                variants={itemVariants}
              >
                <div className="flex items-center justify-between">
                  <div>
                    <div className="font-semibold text-white">{ed.school}</div>
                    <div className="text-sm text-indigo-300">{ed.detail}</div>
                  </div>
                  <div className="text-sm text-indigo-400">{ed.period}</div>
                </div>
              </motion.div>
            ))}
          </div>
        </Section>

        {/* CERTIFICATIONS SECTION */}
        <Section id="certifications" title="Certifications">
          <div className="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
            {portfolioData.certifications.map((c, i) => (
              <motion.div 
                key={i} 
                className="rounded-lg border border-indigo-700 bg-indigo-900/50 p-4 text-white"
                variants={itemVariants}
              >
                <div className="font-medium text-cyan-300">{c.title}</div>
                <div className="text-sm text-indigo-400">{c.org} • {c.year}</div>
              </motion.div>
            ))}
          </div>
        </Section>

        {/* TESTIMONIALS SECTION */}
        <Section id="testimonials" title="Testimonials">
          <div className="grid md:grid-cols-2 gap-4">
            {portfolioData.testimonials.map((t, i) => (
              <motion.div 
                key={i} 
                className="rounded-lg border border-indigo-700 bg-gray-800/50 p-6"
                variants={itemVariants}
              >
                <p className="text-md text-indigo-100">“{t.quote}”</p>
                <div className="mt-3 text-sm text-cyan-400 font-medium">— {t.author}</div>
              </motion.div>
            ))}
          </div>
        </Section>


        {/* CONTACT SECTION */}
        <Section id="contact" title="Get in Touch">
          <div className="grid md:grid-cols-2 gap-10">
            <motion.div variants={itemVariants}>
              <p className="text-indigo-200 text-md mb-6">Interested in collaborating on a unique AI automation project? Drop me a message below or connect via LinkedIn.</p>
              <div className="space-y-3 text-sm">
                <div className="flex items-center gap-3 text-cyan-400 font-medium"><Mail className="w-5 h-5" /> {portfolioData.email}</div>
                <div className="flex items-center gap-3 text-indigo-300"><Linkedin className="w-5 h-5" /> LinkedIn DMs preferred for quick contact</div>
              </div>
            </motion.div>
            
            <motion.form 
              onSubmit={(e) => e.preventDefault()} 
              className="space-y-4"
              variants={itemVariants}
            >
              <div className="grid grid-cols-2 gap-4">
                <input className="border border-indigo-600 rounded px-4 py-2 bg-gray-800 text-white placeholder-indigo-400 focus:outline-none focus:ring-2 focus:ring-cyan-400 focus:border-cyan-400" placeholder="Your name" required />
                <input className="border border-indigo-600 rounded px-4 py-2 bg-gray-800 text-white placeholder-indigo-400 focus:outline-none focus:ring-2 focus:ring-cyan-400 focus:border-cyan-400" type="email" placeholder="Your email" required />
              </div>
              <input className="w-full border border-indigo-600 rounded px-4 py-2 bg-gray-800 text-white placeholder-indigo-400 focus:outline-none focus:ring-2 focus:ring-cyan-400 focus:border-cyan-400" placeholder="Subject" required />
              <textarea className="w-full border border-indigo-600 rounded p-4 bg-gray-800 text-white placeholder-indigo-400 focus:outline-none focus:ring-2 focus:ring-cyan-400 focus:border-cyan-400" placeholder="Your message" rows={5} required />
              <motion.button 
                type="submit" 
                className="inline-flex items-center gap-2 px-6 py-3 rounded-full bg-cyan-400 text-gray-900 font-bold transition-all"
                whileHover={{ scale: 1.05, boxShadow: "0 5px 15px rgba(0, 255, 255, 0.4)" }}
              >
                Send Message <ArrowRight className="w-4 h-4" />
              </motion.button>
            </motion.form>
          </div>
        </Section>

        {/* RESUME SECTION (Simplified for visual brevity) */}
        <section id="resume" className="max-w-5xl mx-auto px-4 py-12">
          <motion.h2 variants={itemVariants} className="text-2xl font-semibold mb-6 text-white border-b border-indigo-700 pb-2">Resume Summary</motion.h2>
          <motion.div variants={itemVariants} className="rounded-xl border border-indigo-700 bg-gray-800/50 p-6 text-sm">
            <p className="font-bold text-cyan-300">Summary</p>
            <p className="text-indigo-200 mt-2">I am an AI enthusiast and automation builder with hands-on experience building mini tools and dashboards using Python, Excel and generative AI. Actively seeking remote internship or part-time roles to grow practical experience.</p>
          </motion.div>
        </section>
      </main>

      {/* Footer */}
      <footer className="border-t border-indigo-700 mt-16 bg-gray-900/80 backdrop-blur-sm">
        <div className="max-w-5xl mx-auto px-4 py-6 text-xs text-indigo-400 flex items-center justify-between">
          <div>© {new Date().getFullYear()} {portfolioData.name}. All rights reserved. Built with React and AI enthusiasm.</div>
          <a href="#home" className="hover:text-cyan-400 transition-colors">↑ Back to top</a>
        </div>
      </footer>
    </div>
  );
}
