import React, { useState, useEffect, useRef } from 'react';
import { ArrowUpRight, BookOpen, Linkedin, Mail } from 'lucide-react';

// --- 노션 콘텐츠 플레이스홀더 ---
const PORTFOLIO_DATA = {
  name: "최서연 Seoyeon Choi",
  role: "Content Manager",
  bio: "안녕하세요, 유연하게 소통하는 Content Manager 최서연입니다. 경청하는 소통, 애정을 담은 설계, 데이터 중심 기획으로 고객들께 더 매력적이고 인상적인 이야기와 경험을 전달합니다. 매사에 진심을 다하고 과정을 소중히 하는 동료가 되겠습니다.",
  skills: [
    "Content Planning", "QA Testing", "Data Analysis (DAU)", "Trend Monitoring", "Jira", "Test Automation", "Localization (EN/KR)"
  ],
  projects: [
    {
      id: "01",
      title: "Nexon Networks",
      category: "QA & Localization",
      description: "신규 개발 게임 QA (웹, iOS/AOS, PC 콘솔). Jira를 통한 실시간 버그 리포트, 테스트 자동화(비속어 필터링, 로그인 플로우), 해외 지사 협업을 위한 통/번역 지원.",
      year: "Experience"
    },
    {
      id: "02",
      title: "Naver Snow",
      category: "Content Planning & Data",
      description: "글로벌/한국 메인 템플릿 기획 및 제작. DAU 등 지표 분석을 통한 기획안 작성. SNS 실시간 트렌드 모니터링 대응 및 글로벌 루키 크리에이터 선정/관리.",
      year: "Experience"
    },
    {
      id: "03",
      title: "Project Management",
      category: "Communication & Scheduling",
      description: "효율적이지만 친절한 시간 계산. 다양한 분야(개발, 3D, 미술)와의 협업에서 플로우 차트와 스케줄링을 통해 팀원들의 스트레스를 줄이고 원활한 소통을 이끌어냅니다.",
      year: "Why Me"
    },
    {
      id: "04",
      title: "Trend & User Experience",
      category: "Daily Archive",
      description: "토스/미래에셋 등 금융 앱 및 X, 인스타그램, 유튜브 등 다양한 커뮤니티 앱 주력 사용. 마비노기, 원스 휴먼, 젠레스 존 제로 등 폭넓은 장르의 게임 플레이 및 트렌드 분석.",
      year: "Interests"
    }
  ],
  contact: {
    email: "01.ad.astra@gmail.com",
    linkedin: "#",
    blog: "https://blog.naver.com/ribo_ovo"
  }
};

export default function App() {
  const [mousePos, setMousePos] = useState({ x: 0, y: 0 });
  const [isHovering, setIsHovering] = useState(false);
  const containerRef = useRef(null);

  // 마우스 위치 추적 및 커스텀 커서 로직
  useEffect(() => {
    const handleMouseMove = (e) => {
      // 그라데이션 위치 업데이트를 위한 CSS 변수 설정
      if (containerRef.current) {
        const { left, top } = containerRef.current.getBoundingClientRect();
        const x = e.clientX - left;
        const y = e.clientY - top;
        containerRef.current.style.setProperty('--mouse-x', `${x}px`);
        containerRef.current.style.setProperty('--mouse-y', `${y}px`);
      }
      setMousePos({ x: e.clientX, y: e.clientY });
    };

    window.addEventListener('mousemove', handleMouseMove);
    return () => window.removeEventListener('mousemove', handleMouseMove);
  }, []);

  // 인터랙티브 요소 호버 이벤트 핸들러
  const handleMouseEnter = () => setIsHovering(true);
  const handleMouseLeave = () => setIsHovering(false);

  return (
    <div 
      ref={containerRef}
      className="relative min-h-screen bg-white text-[#0A192F] font-sans selection:bg-[#0047FF] selection:text-white overflow-hidden"
      style={{
        // 노이즈 텍스처 (Base64)
        backgroundImage: `url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.8' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)' opacity='0.05'/%3E%3C/svg%3E")`,
      }}
    >
      {/* 동적 파란색 그라데이션 배경 (마우스 추적) */}
      <div 
        className="pointer-events-none absolute inset-0 z-0 transition-opacity duration-300"
        style={{
          background: `radial-gradient(800px circle at var(--mouse-x, 50%) var(--mouse-y, 50%), rgba(0, 71, 255, 0.08), transparent 40%)`
        }}
      />

      {/* 커스텀 커서 */}
      <div 
        className={`pointer-events-none fixed top-0 left-0 z-50 rounded-full mix-blend-difference transition-all duration-300 ease-out flex items-center justify-center
          ${isHovering ? 'w-16 h-16 bg-white mix-blend-difference' : 'w-4 h-4 bg-[#0047FF]'}`}
        style={{
          transform: `translate(${mousePos.x}px, ${mousePos.y}px) translate(-50%, -50%)`,
        }}
      >
        {isHovering && <span className="text-[#0A192F] text-[10px] font-bold tracking-widest uppercase opacity-100">View</span>}
      </div>

      {/* 메인 콘텐츠 컨테이너 (그리드 프레임) */}
      <div className="relative z-10 max-w-7xl mx-auto min-h-screen border-x border-[#0A192F]/20 flex flex-col">
        
        {/* Header / Nav */}
        <header className="border-b border-[#0A192F]/20 p-6 md:p-10 flex justify-between items-start md:items-center flex-col md:flex-row gap-6">
          <div>
            <h1 className="text-xl md:text-2xl font-semibold tracking-tight uppercase">
              {PORTFOLIO_DATA.name}
            </h1>
            <p className="text-sm text-[#0047FF] mt-1 font-medium tracking-wide">
              {PORTFOLIO_DATA.role}
            </p>
          </div>
          <nav className="flex gap-8 text-sm font-medium uppercase tracking-wider">
            <a href="#about" className="hover:text-[#0047FF] transition-colors" onMouseEnter={handleMouseEnter} onMouseLeave={handleMouseLeave}>About</a>
            <a href="#work" className="hover:text-[#0047FF] transition-colors" onMouseEnter={handleMouseEnter} onMouseLeave={handleMouseLeave}>Work</a>
            <a href="#contact" className="hover:text-[#0047FF] transition-colors" onMouseEnter={handleMouseEnter} onMouseLeave={handleMouseLeave}>Contact</a>
          </nav>
        </header>

        {/* Main Grid Layout */}
        <main className="flex-grow grid grid-cols-1 lg:grid-cols-12 divide-y lg:divide-y-0 lg:divide-x divide-[#0A192F]/20">
          
          {/* Left Column: Intro & Skills (Spans 4 cols) */}
          <div className="lg:col-span-4 flex flex-col divide-y divide-[#0A192F]/20">
            
            {/* Intro Block */}
            <section id="about" className="p-6 md:p-10 h-full flex flex-col justify-center min-h-[40vh]">
              {/* H2-H3 사이즈의 절제된 타이틀 */}
              <h2 className="text-2xl md:text-3xl font-light leading-snug tracking-tight mb-8">
                Content Management<br />
                <span className="font-semibold text-[#0047FF]">Communication & Data.</span>
              </h2>
              <p className="text-sm md:text-base leading-relaxed text-[#0A192F]/70 mb-12">
                {PORTFOLIO_DATA.bio}
              </p>
              
              <div className="mt-auto">
                <a 
                  href="#contact" 
                  className="inline-flex items-center gap-2 text-sm font-bold uppercase tracking-widest text-[#0047FF] group"
                  onMouseEnter={handleMouseEnter} 
                  onMouseLeave={handleMouseLeave}
                >
                  <span className="border-b border-transparent group-hover:border-[#0047FF] transition-colors">Let's Connect</span>
                  <ArrowUpRight size={16} className="group-hover:translate-x-1 group-hover:-translate-y-1 transition-transform" />
                </a>
              </div>
            </section>

            {/* Skills Block */}
            <section className="p-6 md:p-10 bg-[#f8f9fa]">
              <h3 className="text-xs font-bold uppercase tracking-widest text-[#0A192F]/50 mb-6">Capabilities</h3>
              <div className="flex flex-wrap gap-2">
                {PORTFOLIO_DATA.skills.map((skill, index) => (
                  <span 
                    key={index}
                    className="px-3 py-1.5 border border-[#0A192F]/10 rounded-full text-xs font-medium bg-white text-[#0A192F]"
                  >
                    {skill}
                  </span>
                ))}
              </div>
            </section>
          </div>

          {/* Right Column: Projects List (Spans 8 cols) */}
          <div className="lg:col-span-8">
            <section id="work" className="h-full flex flex-col">
              <div className="p-6 md:p-10 border-b border-[#0A192F]/20">
                <h3 className="text-xl md:text-2xl font-semibold tracking-tight">Experience & Works</h3>
              </div>
              
              <div className="flex-grow flex flex-col divide-y divide-[#0A192F]/20">
                {PORTFOLIO_DATA.projects.map((project) => (
                  <article 
                    key={project.id}
                    className="group relative p-6 md:p-10 hover:bg-[#0047FF] transition-colors duration-500 overflow-hidden flex flex-col md:flex-row md:items-end justify-between gap-6"
                    onMouseEnter={handleMouseEnter}
                    onMouseLeave={handleMouseLeave}
                  >
                    {/* 호버 시 나타나는 미세한 노이즈 오버레이 */}
                    <div className="absolute inset-0 opacity-0 group-hover:opacity-20 transition-opacity duration-500 pointer-events-none"
                         style={{ backgroundImage: `url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noiseFilter'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='1.5' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noiseFilter)'/%3E%3C/svg%3E")` }}
                    />
                    
                    <div className="relative z-10 max-w-xl">
                      <div className="flex items-center gap-4 mb-4">
                        <span className="text-xs font-mono text-[#0A192F]/50 group-hover:text-white/70 transition-colors">
                          {project.id}
                        </span>
                        <span className="text-xs font-bold uppercase tracking-widest text-[#0047FF] group-hover:text-white/90 transition-colors">
                          {project.category}
                        </span>
                      </div>
                      <h4 className="text-2xl md:text-3xl font-medium mb-3 group-hover:text-white transition-colors">
                        {project.title}
                      </h4>
                      <p className="text-sm md:text-base text-[#0A192F]/60 group-hover:text-white/80 transition-colors leading-relaxed line-clamp-2 md:line-clamp-none">
                        {project.description}
                      </p>
                    </div>

                    <div className="relative z-10 shrink-0 flex items-center gap-4 text-[#0A192F]/40 group-hover:text-white transition-colors">
                      <span className="text-sm font-mono">{project.year}</span>
                      <div className="w-10 h-10 rounded-full border border-current flex items-center justify-center opacity-0 group-hover:opacity-100 -translate-x-4 group-hover:translate-x-0 transition-all duration-300">
                        <ArrowUpRight size={18} />
                      </div>
                    </div>
                  </article>
                ))}
              </div>
            </section>
          </div>
        </main>

        {/* Footer / Contact */}
        <footer id="contact" className="border-t border-[#0A192F]/20 grid grid-cols-1 md:grid-cols-2 divide-y md:divide-y-0 md:divide-x divide-[#0A192F]/20">
          <div className="p-6 md:p-10 flex flex-col justify-center">
            <h3 className="text-xs font-bold uppercase tracking-widest text-[#0A192F]/50 mb-4">Get in touch</h3>
            <a 
              href={`mailto:${PORTFOLIO_DATA.contact.email}`}
              className="text-xl md:text-2xl font-light hover:text-[#0047FF] transition-colors inline-block"
              onMouseEnter={handleMouseEnter}
              onMouseLeave={handleMouseLeave}
            >
              {PORTFOLIO_DATA.contact.email}
            </a>
          </div>
          
          <div className="p-6 md:p-10 flex flex-col justify-center bg-[#f8f9fa]">
            <h3 className="text-xs font-bold uppercase tracking-widest text-[#0A192F]/50 mb-4">Socials & Blog</h3>
            <div className="flex gap-6">
              <a href={PORTFOLIO_DATA.contact.linkedin} className="flex items-center gap-2 text-sm font-medium hover:text-[#0047FF] transition-colors group" onMouseEnter={handleMouseEnter} onMouseLeave={handleMouseLeave}>
                <Linkedin size={18} className="text-[#0A192F]/60 group-hover:text-[#0047FF]" />
                LinkedIn
              </a>
              <a href={PORTFOLIO_DATA.contact.blog} target="_blank" rel="noreferrer" className="flex items-center gap-2 text-sm font-medium hover:text-[#0047FF] transition-colors group" onMouseEnter={handleMouseEnter} onMouseLeave={handleMouseLeave}>
                <BookOpen size={18} className="text-[#0A192F]/60 group-hover:text-[#0047FF]" />
                Blog
              </a>
            </div>
          </div>
        </footer>
      </div>

      {/* 모바일 환경에서 커스텀 커서 숨김 처리 및 기본 스크롤 보장 위한 글로벌 스타일 */}
      <style dangerouslySetInnerHTML={{__html: `
        @media (hover: none) and (pointer: coarse) {
          .pointer-events-none.fixed.z-50 { display: none; }
        }
        html { scroll-behavior: smooth; }
        body { cursor: none; }
        a, button { cursor: none; }
        @media (max-width: 768px) {
           body { cursor: auto; }
           a, button { cursor: pointer; }
        }
      `}} />
    </div>
  );
}
