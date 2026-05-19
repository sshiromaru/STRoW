import { useState, useEffect, useRef, useMemo } from "react";

// ─────────────────────────────────────────────
// INITIAL DATA
// ─────────────────────────────────────────────
const INIT_USERS = [
  { id:"u1", name:"田中 太郎", email:"tanaka@company.com", role:"admin", password:"admin123", locked:false, createdAt:"2025-01-10" },
  { id:"u2", name:"佐藤 花子", email:"sato@company.com",   role:"user",  password:"user123",  locked:false, createdAt:"2025-01-15" },
  { id:"u3", name:"鈴木 次郎", email:"suzuki@company.com", role:"user",  password:"user123",  locked:false, createdAt:"2025-02-01" },
  { id:"u4", name:"山田 三郎", email:"yamada@company.com", role:"user",  password:"user123",  locked:true,  createdAt:"2025-03-01" },
];
const INIT_HISTORY = [
  { id:"h1", name:"田中 太郎", email:"tanaka@company.com", at:"2025-05-19 09:02", result:"success", ip:"192.168.1.10" },
  { id:"h2", name:"佐藤 花子", email:"sato@company.com",   at:"2025-05-19 08:45", result:"success", ip:"192.168.1.11" },
  { id:"h3", name:"山田 三郎", email:"yamada@company.com", at:"2025-05-18 17:30", result:"fail",    ip:"192.168.1.20" },
  { id:"h4", name:"山田 三郎", email:"yamada@company.com", at:"2025-05-18 17:31", result:"fail",    ip:"192.168.1.20" },
  { id:"h5", name:"山田 三郎", email:"yamada@company.com", at:"2025-05-18 17:32", result:"locked",  ip:"192.168.1.20" },
  { id:"h6", name:"鈴木 次郎", email:"suzuki@company.com", at:"2025-05-18 14:10", result:"success", ip:"192.168.1.12" },
];
const INIT_GOALS = { sales:30000000, grossProfit:10000000 };
const INIT_PROJECTS = [
  {
    id:"PJ-2025-001", name:"ABCシステム開発", client:"株式会社ABC", clientDept:"情報システム部",
    manager:"田中 太郎", status:"inProgress", currency:"JPY", category:"システム開発",
    description:"基幹システムのクラウド移行・リプレース案件。API連携、データ移行含む。",
    probability:100, startDate:"2025-04-01", endDate:"2025-09-30", createdAt:"2025-03-15",
    sales:[
      { id:"s1", desc:"初期開発費（第1フェーズ）", amount:3000000, taxType:"external", taxRate:10, invoiceNo:"INV-2025-0501", invoiceDate:"2025-05-01", dueDate:"2025-05-31", paid:true },
      { id:"s2", desc:"追加開発費（第2フェーズ）", amount:1500000, taxType:"external", taxRate:10, invoiceNo:"INV-2025-0801", invoiceDate:"2025-08-01", dueDate:"2025-08-31", paid:false },
      { id:"s3", desc:"年間保守費用",             amount:500000,  taxType:"external", taxRate:10, invoiceNo:"INV-2025-0901", invoiceDate:"2025-09-01", dueDate:"2025-09-30", paid:false },
    ],
    purchases:[
      { id:"p1", desc:"クラウドインフラ費（AWS）", supplier:"AWS Japan合同会社",   amount:800000,  taxType:"external", taxRate:10, dueDate:"2025-05-31", paid:true },
      { id:"p2", desc:"外注開発費",               supplier:"株式会社デブ技研",     amount:1200000, taxType:"external", taxRate:10, dueDate:"2025-08-31", paid:false },
    ],
  },
  {
    id:"PJ-2025-002", name:"XYZコンサルティング", client:"XYZ商事株式会社", clientDept:"経営企画部",
    manager:"佐藤 花子", status:"ordered", currency:"JPY", category:"コンサルティング",
    description:"業務プロセス改善コンサルティング。現状分析〜改善提案〜実装支援。",
    probability:100, startDate:"2025-05-01", endDate:"2025-07-31", createdAt:"2025-04-20",
    sales:[
      { id:"s4", desc:"コンサルティング料（内税）", amount:2400000, taxType:"internal", taxRate:10, invoiceNo:"INV-2025-0701", invoiceDate:"2025-07-01", dueDate:"2025-07-31", paid:false },
    ],
    purchases:[
      { id:"p3", desc:"外部コンサル費用", supplier:"戦略経営研究所", amount:500000, taxType:"external", taxRate:10, dueDate:"2025-07-31", paid:false },
    ],
  },
  {
    id:"PJ-2025-003", name:"DEF設備導入プロジェクト", client:"DEF工業株式会社", clientDept:"製造部",
    manager:"鈴木 次郎", status:"completed", currency:"JPY", category:"設備導入",
    description:"製造ライン自動化設備の導入・設置・トレーニング。3ヶ月完工。",
    probability:100, startDate:"2025-01-01", endDate:"2025-03-31", createdAt:"2024-12-01",
    sales:[
      { id:"s5", desc:"設備費",        amount:6000000, taxType:"external", taxRate:10, invoiceNo:"INV-2025-0201", invoiceDate:"2025-01-31", dueDate:"2025-02-28", paid:true },
      { id:"s6", desc:"設置工事費",    amount:1500000, taxType:"external", taxRate:10, invoiceNo:"INV-2025-0301", invoiceDate:"2025-03-15", dueDate:"2025-03-31", paid:true },
      { id:"s7", desc:"トレーニング費", amount:500000,  taxType:"external", taxRate:10, invoiceNo:"INV-2025-0302", invoiceDate:"2025-03-31", dueDate:"2025-04-30", paid:true },
    ],
    purchases:[
      { id:"p4", desc:"機器仕入れ",   supplier:"産業機械株式会社",       amount:4500000, taxType:"external", taxRate:10, dueDate:"2025-02-28", paid:true },
      { id:"p5", desc:"工事外注費",   supplier:"日本電気工事株式会社",   amount:800000,  taxType:"external", taxRate:10, dueDate:"2025-03-31", paid:true },
    ],
  },
  {
    id:"PJ-2025-004", name:"MNO Overseas EC System", client:"MNO International LLC", clientDept:"Digital Team",
    manager:"田中 太郎", status:"inProgress", currency:"USD", category:"システム開発",
    description:"Overseas EC platform development for North American market.",
    probability:100, startDate:"2025-04-01", endDate:"2025-12-31", createdAt:"2025-03-20",
    sales:[
      { id:"s8", desc:"System Development",    amount:35000, taxType:"none", taxRate:0, invoiceNo:"INV-2025-US01", invoiceDate:"2025-06-01", dueDate:"2025-06-30", paid:true },
      { id:"s9", desc:"Annual Maintenance Fee", amount:10000, taxType:"none", taxRate:0, invoiceNo:"INV-2025-US02", invoiceDate:"2025-12-01", dueDate:"2025-12-31", paid:false },
    ],
    purchases:[
      { id:"p6", desc:"Offshore Development", supplier:"TechVN Co., Ltd.", amount:20000, taxType:"none", taxRate:0, dueDate:"2025-06-30", paid:true },
    ],
  },
  {
    id:"PJ-2025-005", name:"JKLウェブサイトリニューアル", client:"JKL株式会社", clientDept:"マーケティング部",
    manager:"佐藤 花子", status:"quote", currency:"JPY", category:"ウェブ制作",
    description:"コーポレートサイト全面リニューアル。WordPress + Headless構成を提案中。",
    probability:60, startDate:"2025-07-01", endDate:"2025-09-30", createdAt:"2025-05-10",
    sales:[
      { id:"s10", desc:"ウェブサイト制作費", amount:980000, taxType:"external", taxRate:10, invoiceNo:"", invoiceDate:"2025-09-30", dueDate:"2025-10-31", paid:false },
    ],
    purchases:[
      { id:"p7", desc:"デザイン外注費", supplier:"クリエイティブスタジオ合同会社", amount:300000, taxType:"external", taxRate:10, dueDate:"2025-09-30", paid:false },
    ],
  },
  {
    id:"PJ-2025-006", name:"GHI保守契約FY2025", client:"GHI製作所", clientDept:"IT管理部",
    manager:"鈴木 次郎", status:"inProgress", currency:"JPY", category:"保守",
    description:"既存システムの年間保守契約。月次定例含む。",
    probability:100, startDate:"2025-04-01", endDate:"2026-03-31", createdAt:"2025-03-25",
    sales:[
      { id:"s11", desc:"上半期保守費（4〜9月）", amount:600000, taxType:"external", taxRate:10, invoiceNo:"INV-2025-0401", invoiceDate:"2025-04-01", dueDate:"2025-04-30", paid:true },
      { id:"s12", desc:"下半期保守費（10〜3月）", amount:600000, taxType:"external", taxRate:10, invoiceNo:"", invoiceDate:"2025-10-01", dueDate:"2025-10-31", paid:false },
    ],
    purchases:[],
  },
];

// ─────────────────────────────────────────────
// HELPERS
// ─────────────────────────────────────────────
const fmt = (n, curr="JPY") =>
  curr==="USD" ? "$"+Math.round(n).toLocaleString() : "¥"+Math.round(n).toLocaleString("ja-JP");
const fmtMan = (v) => (v/10000).toLocaleString("ja-JP",{maximumFractionDigits:0})+"万";
const today  = () => new Date().toISOString().slice(0,10);
const nowStr = () => new Date().toLocaleString("ja-JP",{year:"numeric",month:"2-digit",day:"2-digit",hour:"2-digit",minute:"2-digit"}).replace(/\//g,"-");
const uid    = () => Math.random().toString(36).slice(2,9);

const newPjId = (list) => {
  const yr = new Date().getFullYear();
  const nums = list.filter(p=>p.id.startsWith(`PJ-${yr}`)).map(p=>parseInt(p.id.split("-")[2])||0);
  return `PJ-${yr}-${String(nums.length?Math.max(...nums)+1:1).padStart(3,"0")}`;
};

const taxAmt = (amount, taxType, taxRate) => {
  if (!taxRate || taxType==="none") return 0;
  if (taxType==="external") return Math.round(amount*taxRate/100);
  return Math.round(amount - amount/(1+taxRate/100));
};
const calcStats = (p) => {
  const salesBase = p.sales.reduce((s,r)=>s+(r.taxType==="internal"?Math.round(r.amount/1.1):r.amount),0);
  const purchBase = p.purchases.reduce((s,r)=>s+(r.taxType==="internal"?Math.round(r.amount/1.1):r.amount),0);
  const salesTax  = p.sales.reduce((s,r)=>s+taxAmt(r.amount,r.taxType,r.taxRate),0);
  const purchTax  = p.purchases.reduce((s,r)=>s+taxAmt(r.amount,r.taxType,r.taxRate),0);
  const grossProfit  = salesBase - purchBase;
  const grossMargin  = salesBase>0 ? grossProfit/salesBase*100 : 0;
  const collectedSales = p.sales.filter(r=>r.paid).reduce((s,r)=>s+(r.taxType==="internal"?Math.round(r.amount/1.1):r.amount),0);
  const paidPurch    = p.purchases.filter(r=>r.paid).reduce((s,r)=>s+(r.taxType==="internal"?Math.round(r.amount/1.1):r.amount),0);
  return {salesBase,purchBase,salesTax,purchTax,grossProfit,grossMargin,collectedSales,paidPurch};
};

const exportCSV = (projects) => {
  const hdr = ["案件ID","案件名","顧客名","担当者","ステータス","通貨","売上合計(税抜)","仕入合計(税抜)","粗利","粗利率(%)","開始日","完了予定日"];
  const rows = projects.map(p => {
    const st = calcStats(p);
    return [p.id,p.name,p.client,p.manager,p.status,p.currency,st.salesBase,st.purchBase,st.grossProfit,st.grossMargin.toFixed(1),p.startDate,p.endDate];
  });
  const csv = [hdr,...rows].map(r=>r.map(c=>`"${String(c??"").replace(/"/g,'""')}"`).join(",")).join("\n");
  const a = document.createElement("a");
  a.href = URL.createObjectURL(new Blob(["\uFEFF"+csv],{type:"text/csv;charset=utf-8;"}));
  a.download = `案件台帳_${today()}.csv`; a.click();
};

// ─────────────────────────────────────────────
// CONSTANTS
// ─────────────────────────────────────────────
const STATUS = {
  quote:      {label:"見積中",   bg:"#FEF3C7",text:"#92400E",dot:"#F59E0B"},
  ordered:    {label:"受注確定", bg:"#E0F2FE",text:"#075985",dot:"#0EA5E9"},
  inProgress: {label:"進行中",   bg:"#EEF2FF",text:"#3730A3",dot:"#6366F1"},
  completed:  {label:"完了",     bg:"#D1FAE5",text:"#065F46",dot:"#10B981"},
  lost:       {label:"失注",     bg:"#F1F5F9",text:"#94A3B8",dot:"#CBD5E1"},
};
const TAX_OPTS = [
  {value:"external|10",label:"外税 10%（標準）"},
  {value:"external|8", label:"外税 8%（軽減）"},
  {value:"internal|10",label:"内税 10%（税込）"},
  {value:"none|0",     label:"非課税 / 免税"},
];
const MANAGER_COLORS = ["#4F46E5","#059669","#D97706","#0891B2","#7C3AED","#DC2626"];
const inp = {width:"100%",border:"1px solid #E2E8F0",borderRadius:8,padding:"9px 11px",fontSize:13,color:"#1E293B",background:"#fff",outline:"none",boxSizing:"border-box"};

// ─────────────────────────────────────────────
// SMALL COMPONENTS
// ─────────────────────────────────────────────
const Badge = ({status}) => {
  const c = STATUS[status]||STATUS.quote;
  return (
    <span style={{display:"inline-flex",alignItems:"center",gap:5,background:c.bg,color:c.text,borderRadius:20,padding:"3px 10px",fontSize:11,fontWeight:700}}>
      <span style={{width:6,height:6,borderRadius:"50%",background:c.dot,display:"inline-block"}}/>
      {c.label}
    </span>
  );
};
const Lbl = ({children,required}) => (
  <div style={{fontSize:11,fontWeight:700,color:"#64748B",marginBottom:5,textTransform:"uppercase",letterSpacing:0.5}}>
    {children}{required && <span style={{color:"#EF4444",marginLeft:2}}>*</span>}
  </div>
);
const Field = ({label,required,children,col}) => (
  <div style={{gridColumn:col}}>
    <Lbl required={required}>{label}</Lbl>
    {children}
  </div>
);
const BtnRow = ({onCancel,onOk,okLabel,okColor="#4F46E5",disabled}) => (
  <div style={{display:"flex",justifyContent:"flex-end",gap:8,marginTop:22,paddingTop:18,borderTop:"1px solid #F1F5F9"}}>
    <button onClick={onCancel} style={{fontSize:13,color:"#475569",border:"1px solid #E2E8F0",background:"#fff",borderRadius:8,padding:"8px 18px",cursor:"pointer"}}>キャンセル</button>
    <button onClick={onOk} disabled={disabled} style={{fontSize:13,fontWeight:700,color:"#fff",background:disabled?"#A5B4FC":okColor,border:"none",borderRadius:8,padding:"8px 20px",cursor:disabled?"default":"pointer"}}>{okLabel}</button>
  </div>
);

// ─────────────────────────────────────────────
// MODAL WRAPPER
// ─────────────────────────────────────────────
const Modal = ({title,subtitle,onClose,children,width=520}) => (
  <div style={{position:"fixed",inset:0,zIndex:200,display:"flex",alignItems:"center",justifyContent:"center"}}>
    <div style={{position:"absolute",inset:0,background:"rgba(15,23,42,0.45)"}} onClick={onClose}/>
    <div style={{position:"relative",background:"#fff",borderRadius:16,width:"100%",maxWidth:width,margin:"0 16px",maxHeight:"90vh",display:"flex",flexDirection:"column",boxShadow:"0 32px 64px rgba(0,0,0,0.18)"}}>
      <div style={{padding:"18px 24px 14px",borderBottom:"1px solid #F1F5F9",display:"flex",alignItems:"flex-start",justifyContent:"space-between"}}>
        <div>
          <div style={{fontSize:15,fontWeight:700,color:"#1E293B"}}>{title}</div>
          {subtitle && <div style={{fontSize:12,color:"#94A3B8",marginTop:2}}>{subtitle}</div>}
        </div>
        <button onClick={onClose} style={{background:"#F8FAFC",border:"none",cursor:"pointer",color:"#64748B",width:28,height:28,borderRadius:"50%",fontSize:16,lineHeight:"28px",textAlign:"center",flexShrink:0}}>×</button>
      </div>
      <div style={{flex:1,overflowY:"auto",padding:"20px 24px"}}>{children}</div>
    </div>
  </div>
);

// ─────────────────────────────────────────────
// LOGIN
// ─────────────────────────────────────────────
const LoginScreen = ({users,onLogin,onAddHistory}) => {
  const [email,setEmail]   = useState("");
  const [pw,setPw]         = useState("");
  const [showPw,setShowPw] = useState(false);
  const [error,setError]   = useState("");

  const handleLogin = () => {
    setError("");
    const u = users.find(u=>u.email===email);
    if (!u) { setError("メールアドレスが見つかりません"); return; }
    if (u.locked) {
      onAddHistory({id:uid(),name:u.name,email:u.email,at:nowStr(),result:"locked",ip:"192.168.1.x"});
      setError("アカウントがロックされています。管理者に解除を依頼してください。"); return;
    }
    if (u.password!==pw) {
      onAddHistory({id:uid(),name:u.name,email:u.email,at:nowStr(),result:"fail",ip:"192.168.1.x"});
      setError("パスワードが正しくありません"); return;
    }
    onAddHistory({id:uid(),name:u.name,email:u.email,at:nowStr(),result:"success",ip:"192.168.1.x"});
    onLogin(u);
  };

  return (
    <div style={{minHeight:"100vh",background:"#F8FAFC",display:"flex",alignItems:"center",justifyContent:"center",fontFamily:"-apple-system,BlinkMacSystemFont,'Hiragino Kaku Gothic Pro','Yu Gothic',sans-serif"}}>
      <div style={{width:"100%",maxWidth:400,padding:"0 20px"}}>
        <div style={{textAlign:"center",marginBottom:32}}>
          <div style={{display:"inline-flex",alignItems:"center",justifyContent:"center",width:52,height:52,background:"#4F46E5",borderRadius:14,marginBottom:16}}>
            <span style={{fontSize:24,color:"#fff"}}>▣</span>
          </div>
          <div style={{fontSize:22,fontWeight:800,color:"#1E293B",letterSpacing:-0.5}}>案件管理台帳</div>
          <div style={{fontSize:13,color:"#94A3B8",marginTop:4}}>Project Ledger</div>
        </div>
        <div style={{background:"#fff",borderRadius:16,border:"1px solid #F1F5F9",padding:"28px 28px 24px",boxShadow:"0 4px 24px rgba(0,0,0,0.06)"}}>
          <div style={{marginBottom:18}}>
            <Lbl>メールアドレス</Lbl>
            <input style={inp} type="email" value={email} onChange={e=>setEmail(e.target.value)} placeholder="your@company.com" onKeyDown={e=>e.key==="Enter"&&handleLogin()}/>
          </div>
          <div style={{marginBottom:20}}>
            <Lbl>パスワード</Lbl>
            <div style={{position:"relative"}}>
              <input style={{...inp,paddingRight:40}} type={showPw?"text":"password"} value={pw} onChange={e=>setPw(e.target.value)} placeholder="••••••••" onKeyDown={e=>e.key==="Enter"&&handleLogin()}/>
              <button onClick={()=>setShowPw(v=>!v)} style={{position:"absolute",right:10,top:"50%",transform:"translateY(-50%)",background:"none",border:"none",color:"#94A3B8",cursor:"pointer",fontSize:12}}>{showPw?"隠す":"表示"}</button>
            </div>
          </div>
          {error && <div style={{marginBottom:14,padding:"10px 12px",background:"#FEF2F2",border:"1px solid #FECACA",borderRadius:8,fontSize:12,color:"#DC2626"}}>{error}</div>}
          <button onClick={handleLogin} style={{width:"100%",padding:"11px 0",fontSize:14,fontWeight:700,color:"#fff",background:"#4F46E5",border:"none",borderRadius:10,cursor:"pointer"}}>ログイン</button>
        </div>
        <div style={{marginTop:20,background:"#EEF2FF",border:"1px solid #C7D2FE",borderRadius:10,padding:"12px 16px",fontSize:12,color:"#4F46E5"}}>
          <div style={{fontWeight:700,marginBottom:6}}>デモ用アカウント</div>
          <div>管理者: tanaka@company.com / admin123</div>
          <div style={{marginTop:3}}>一般: sato@company.com / user123</div>
          <div style={{marginTop:3,color:"#7C3AED"}}>ロック中: yamada@company.com</div>
        </div>
      </div>
    </div>
  );
};

// ─────────────────────────────────────────────
// DONUT CHART
// ─────────────────────────────────────────────
const DonutChart = ({actual,target,color,size=112,stroke=11}) => {
  const ref = useRef(null);
  const pct = target>0 ? Math.min(actual/target,1) : 0;
  useEffect(()=>{
    const c = ref.current; if(!c) return;
    const ctx = c.getContext("2d");
    const cx=size/2, cy=size/2, r=size/2-stroke;
    ctx.clearRect(0,0,size,size);
    ctx.beginPath(); ctx.arc(cx,cy,r,0,Math.PI*2); ctx.strokeStyle="#F1F5F9"; ctx.lineWidth=stroke; ctx.stroke();
    if (pct>0) {
      ctx.beginPath(); ctx.arc(cx,cy,r,-Math.PI/2,-Math.PI/2+Math.PI*2*pct);
      ctx.strokeStyle=color; ctx.lineWidth=stroke; ctx.lineCap="round"; ctx.stroke();
    }
  },[pct,color,size,stroke]);
  return (
    <div style={{position:"relative",width:size,height:size,flexShrink:0}}>
      <canvas ref={ref} width={size} height={size}/>
      <div style={{position:"absolute",inset:0,display:"flex",flexDirection:"column",alignItems:"center",justifyContent:"center"}}>
        <div style={{fontSize:17,fontWeight:800,color:"#1E293B",lineHeight:1}}>{Math.round(pct*100)}%</div>
        <div style={{fontSize:10,color:"#94A3B8",marginTop:2}}>達成率</div>
      </div>
    </div>
  );
};

// ─────────────────────────────────────────────
// GOAL CARD (donut + bar)
// ─────────────────────────────────────────────
const GoalCard = ({label,actual,target,color}) => {
  const pct = target>0 ? Math.min(actual/target*100,100) : 0;
  const rem = Math.max(target-actual,0);
  const ticks = [0,target/2,target].map(v=>"¥"+fmtMan(v));
  return (
    <div style={{background:"#fff",border:"1px solid #F1F5F9",borderRadius:12,padding:"16px 18px",display:"flex",flexDirection:"column",gap:14}}>
      <div style={{fontSize:11,fontWeight:700,color:"#64748B",textTransform:"uppercase",letterSpacing:0.5}}>{label}</div>
      <div style={{display:"flex",alignItems:"center",gap:18}}>
        <DonutChart actual={actual} target={target} color={color}/>
        <div style={{flex:1,display:"flex",flexDirection:"column",gap:6}}>
          {[{label:"目標",value:fmtMan(target),color:"#94A3B8"},{label:"実績",value:fmtMan(actual),color},{label:"残り",value:fmtMan(rem),color:"#CBD5E1"}].map(r=>(
            <div key={r.label} style={{display:"flex",justifyContent:"space-between",alignItems:"baseline"}}>
              <span style={{fontSize:11,color:"#94A3B8"}}>{r.label}</span>
              <span style={{fontSize:14,fontWeight:700,color:r.color,fontVariantNumeric:"tabular-nums"}}>¥{r.value}</span>
            </div>
          ))}
        </div>
      </div>
      <div>
        <div style={{height:24,background:"#F8FAFC",borderRadius:6,overflow:"hidden",position:"relative"}}>
          <div style={{height:"100%",width:`${Math.max(pct,pct>0?3:0)}%`,background:color,borderRadius:6,display:"flex",alignItems:"center",justifyContent:"flex-end",paddingRight:pct>12?8:0}}>
            {pct>12 && <span style={{fontSize:11,fontWeight:700,color:"#fff"}}>{Math.round(pct)}%</span>}
          </div>
          {pct<=12 && pct>0 && <span style={{position:"absolute",left:`${pct+1}%`,top:"50%",transform:"translateY(-50%)",fontSize:11,fontWeight:700,color}}>{Math.round(pct)}%</span>}
        </div>
        <div style={{display:"flex",justifyContent:"space-between",marginTop:4,fontSize:10,color:"#CBD5E1"}}>
          {ticks.map((t,i)=><span key={i}>{t}</span>)}
        </div>
      </div>
    </div>
  );
};

// ─────────────────────────────────────────────
// PROJECT FORM (shared by New / Edit)
// ─────────────────────────────────────────────
const ProjectForm = ({title,subtitle,initial,onClose,onSave,projects}) => {
  const [f,setF] = useState(initial);
  const set = (k,v) => setF(p=>({...p,[k]:v}));
  const ok = f.name.trim() && f.client.trim();
  return (
    <Modal title={title} subtitle={subtitle} onClose={onClose} width={620}>
      <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:14}}>
        <Field label="案件名" required col="1/-1"><input style={inp} value={f.name} onChange={e=>set("name",e.target.value)} placeholder="例：ABCシステム開発" autoFocus/></Field>
        <Field label="顧客名" required><input style={inp} value={f.client} onChange={e=>set("client",e.target.value)} placeholder="例：株式会社ABC"/></Field>
        <Field label="部署名"><input style={inp} value={f.clientDept||""} onChange={e=>set("clientDept",e.target.value)} placeholder="例：情報システム部"/></Field>
        <Field label="担当者"><input style={inp} value={f.manager||""} onChange={e=>set("manager",e.target.value)} placeholder="例：田中 太郎"/></Field>
        <Field label="ステータス">
          <select style={inp} value={f.status} onChange={e=>set("status",e.target.value)}>
            {Object.entries(STATUS).map(([k,v])=><option key={k} value={k}>{v.label}</option>)}
          </select>
        </Field>
        <Field label="カテゴリ">
          <select style={inp} value={f.category||""} onChange={e=>set("category",e.target.value)}>
            <option value="">選択</option>
            {["システム開発","コンサルティング","設備導入","ウェブ制作","保守","その他"].map(c=><option key={c}>{c}</option>)}
          </select>
        </Field>
        <Field label="通貨">
          <select style={inp} value={f.currency} onChange={e=>set("currency",e.target.value)}>
            <option value="JPY">JPY（日本円）</option>
            <option value="USD">USD（米ドル）</option>
          </select>
        </Field>
        <Field label="受注確度（%）"><input type="number" min={0} max={100} style={inp} value={f.probability} onChange={e=>set("probability",Number(e.target.value))}/></Field>
        <Field label="開始日"><input type="date" style={inp} value={f.startDate||""} onChange={e=>set("startDate",e.target.value)}/></Field>
        <Field label="完了予定日"><input type="date" style={inp} value={f.endDate||""} onChange={e=>set("endDate",e.target.value)}/></Field>
        <Field label="案件概要" col="1/-1"><textarea rows={3} style={{...inp,resize:"none"}} value={f.description||""} onChange={e=>set("description",e.target.value)} placeholder="案件の内容・背景..."/></Field>
      </div>
      {!subtitle && <div style={{marginTop:14,background:"#F0F4FF",border:"1px solid #C7D2FE",borderRadius:10,padding:"10px 14px",fontSize:12,color:"#4F46E5"}}>登録後、売上明細・仕入明細を入力できます</div>}
      <BtnRow onCancel={onClose} onOk={()=>ok&&onSave(f)} okLabel={subtitle?"変更を保存":"案件を登録 →"} disabled={!ok}/>
    </Modal>
  );
};

// ─────────────────────────────────────────────
// SALE MODAL
// ─────────────────────────────────────────────
const SaleModal = ({project,onClose,onAdd}) => {
  const [f,setF] = useState({desc:"",amount:"",taxKey:"external|10",invoiceNo:"",invoiceDate:today(),dueDate:"",paid:false});
  const set = (k,v) => setF(p=>({...p,[k]:v}));
  const [tt,tr] = f.taxKey.split("|");
  const amtN = Number(f.amount)||0;
  const taxN = taxAmt(amtN,tt,Number(tr));
  const baseN = tt==="internal"?Math.round(amtN/(1+Number(tr)/100)):amtN;
  const ok = f.desc.trim()&&amtN>0;
  const sym = project.currency==="USD"?"$":"¥";
  return (
    <Modal title="② 売上明細を追加" subtitle={`案件：${project.name}`} onClose={onClose} width={520}>
      <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:14}}>
        <Field label="売上内容" required col="1/-1"><input style={inp} value={f.desc} onChange={e=>set("desc",e.target.value)} placeholder="例：システム開発費（第1フェーズ）" autoFocus/></Field>
        <Field label={tt==="internal"?"金額（税込）":"金額（税抜）"} required>
          <div style={{display:"flex",alignItems:"center",gap:6}}><span style={{fontSize:13,color:"#64748B"}}>{sym}</span><input type="number" min={0} style={inp} value={f.amount} onChange={e=>set("amount",e.target.value)} placeholder="0"/></div>
        </Field>
        <Field label="消費税区分">
          <select style={inp} value={f.taxKey} onChange={e=>set("taxKey",e.target.value)}>
            {TAX_OPTS.map(o=><option key={o.value} value={o.value}>{o.label}</option>)}
          </select>
        </Field>
        {amtN>0 && (
          <div style={{gridColumn:"1/-1",background:"#F8FAFC",borderRadius:10,padding:"12px 14px",display:"grid",gridTemplateColumns:"1fr 1fr 1fr",gap:8}}>
            {[{label:"税抜",value:sym+Math.round(baseN).toLocaleString("ja-JP"),c:"#334155"},{label:"消費税",value:"+"+sym+taxN.toLocaleString("ja-JP"),c:"#7C3AED"},{label:"請求総額",value:sym+(tt==="external"?amtN+taxN:amtN).toLocaleString("ja-JP"),c:"#059669"}].map(r=>(
              <div key={r.label}><div style={{fontSize:10,color:"#94A3B8",fontWeight:700,marginBottom:3}}>{r.label}</div><div style={{fontSize:14,fontWeight:700,color:r.c}}>{r.value}</div></div>
            ))}
          </div>
        )}
        <Field label="請求書番号"><input style={inp} value={f.invoiceNo} onChange={e=>set("invoiceNo",e.target.value)} placeholder="INV-2025-001"/></Field>
        <Field label="請求日"><input type="date" style={inp} value={f.invoiceDate} onChange={e=>set("invoiceDate",e.target.value)}/></Field>
        <Field label="入金期日"><input type="date" style={inp} value={f.dueDate} onChange={e=>set("dueDate",e.target.value)}/></Field>
        <Field label="入金状況">
          <select style={inp} value={String(f.paid)} onChange={e=>set("paid",e.target.value==="true")}>
            <option value="false">● 未入金</option><option value="true">✓ 入金済</option>
          </select>
        </Field>
      </div>
      <BtnRow onCancel={onClose} onOk={()=>ok&&onAdd({id:uid(),desc:f.desc,amount:amtN,taxType:tt,taxRate:Number(tr),invoiceNo:f.invoiceNo,invoiceDate:f.invoiceDate,dueDate:f.dueDate,paid:f.paid})} okLabel="売上明細を追加 ＋" disabled={!ok}/>
    </Modal>
  );
};

// ─────────────────────────────────────────────
// PURCHASE MODAL
// ─────────────────────────────────────────────
const PurchaseModal = ({project,onClose,onAdd}) => {
  const [f,setF] = useState({desc:"",supplier:"",amount:"",taxKey:"external|10",dueDate:"",paid:false});
  const set = (k,v) => setF(p=>({...p,[k]:v}));
  const [tt,tr] = f.taxKey.split("|");
  const amtN = Number(f.amount)||0;
  const taxN = taxAmt(amtN,tt,Number(tr));
  const baseN = tt==="internal"?Math.round(amtN/(1+Number(tr)/100)):amtN;
  const ok = f.desc.trim()&&amtN>0;
  const sym = project.currency==="USD"?"$":"¥";
  return (
    <Modal title="③ 仕入明細を追加" subtitle={`案件：${project.name}`} onClose={onClose} width={520}>
      <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:14}}>
        <Field label="仕入内容" required col="1/-1"><input style={inp} value={f.desc} onChange={e=>set("desc",e.target.value)} placeholder="例：外注開発費" autoFocus/></Field>
        <Field label="仕入先" col="1/-1"><input style={inp} value={f.supplier} onChange={e=>set("supplier",e.target.value)} placeholder="例：株式会社○○"/></Field>
        <Field label={tt==="internal"?"金額（税込）":"金額（税抜）"} required>
          <div style={{display:"flex",alignItems:"center",gap:6}}><span style={{fontSize:13,color:"#64748B"}}>{sym}</span><input type="number" min={0} style={inp} value={f.amount} onChange={e=>set("amount",e.target.value)} placeholder="0"/></div>
        </Field>
        <Field label="消費税区分">
          <select style={inp} value={f.taxKey} onChange={e=>set("taxKey",e.target.value)}>
            {TAX_OPTS.map(o=><option key={o.value} value={o.value}>{o.label}</option>)}
          </select>
        </Field>
        {amtN>0 && (
          <div style={{gridColumn:"1/-1",background:"#FEF2F2",borderRadius:10,padding:"12px 14px",display:"grid",gridTemplateColumns:"1fr 1fr 1fr",gap:8}}>
            {[{label:"税抜",value:sym+Math.round(baseN).toLocaleString("ja-JP"),c:"#334155"},{label:"消費税",value:"+"+sym+taxN.toLocaleString("ja-JP"),c:"#7C3AED"},{label:"支払総額",value:sym+(tt==="external"?amtN+taxN:amtN).toLocaleString("ja-JP"),c:"#DC2626"}].map(r=>(
              <div key={r.label}><div style={{fontSize:10,color:"#94A3B8",fontWeight:700,marginBottom:3}}>{r.label}</div><div style={{fontSize:14,fontWeight:700,color:r.c}}>{r.value}</div></div>
            ))}
          </div>
        )}
        <Field label="支払期日" col="1/-1"><input type="date" style={inp} value={f.dueDate} onChange={e=>set("dueDate",e.target.value)}/></Field>
        <Field label="支払状況" col="1/-1">
          <select style={inp} value={String(f.paid)} onChange={e=>set("paid",e.target.value==="true")}>
            <option value="false">● 未払</option><option value="true">✓ 支払済</option>
          </select>
        </Field>
      </div>
      <BtnRow onCancel={onClose} onOk={()=>ok&&onAdd({id:uid(),desc:f.desc,supplier:f.supplier,amount:amtN,taxType:tt,taxRate:Number(tr),dueDate:f.dueDate,paid:f.paid})} okLabel="仕入明細を追加 ＋" okColor="#DC2626" disabled={!ok}/>
    </Modal>
  );
};

// ─────────────────────────────────────────────
// IMPORT MODAL
// ─────────────────────────────────────────────
const ImportModal = ({onClose,onImport,projects}) => {
  const [step,setStep]   = useState("upload");
  const [preview,setPrev]= useState([]);
  const [error,setError] = useState("");
  const fileRef = useRef(null);
  const TEMPLATE = `案件名,顧客名,部署名,担当者,ステータス,カテゴリ,通貨,受注確度,開始日,完了予定日,案件概要\n新規Webシステム,株式会社サンプル,IT部,田中 太郎,quote,システム開発,JPY,80,2025-06-01,2025-12-31,サンプル案件`;
  const dlTemplate = () => {
    const a = document.createElement("a");
    a.href = URL.createObjectURL(new Blob(["\uFEFF"+TEMPLATE],{type:"text/csv;charset=utf-8;"}));
    a.download="案件取込テンプレート.csv"; a.click();
  };
  const handleFile = (file) => {
    if (!file) return; setError("");
    const reader = new FileReader();
    reader.onload = (e) => {
      try {
        let text = e.target.result;
        if (text.charCodeAt(0)===0xFEFF) text=text.slice(1);
        const lines = text.split(/\r?\n/).filter(l=>l.trim());
        if (lines.length<2){setError("データが1件もありません");return;}
        const headers = lines[0].split(",").map(h=>h.replace(/^"|"$/g,"").trim());
        const rows = lines.slice(1).map(line=>{
          const cols = (line.match(/("(?:[^"]|"")*"|[^,]*)/g)||[]).map(c=>c.replace(/^"|"$/g,"").replace(/""/g,'"').trim());
          const obj={};
          headers.forEach((h,i)=>obj[h]=cols[i]||"");
          return obj;
        }).filter(r=>r["案件名"]);
        const parsed = rows.map(r=>({
          id:newPjId([...projects,...preview]),
          name:r["案件名"]||"",client:r["顧客名"]||"",clientDept:r["部署名"]||"",
          manager:r["担当者"]||"",status:r["ステータス"]||"quote",category:r["カテゴリ"]||"",
          currency:r["通貨"]||"JPY",probability:Number(r["受注確度"])||100,
          startDate:r["開始日"]||"",endDate:r["完了予定日"]||"",description:r["案件概要"]||"",
          createdAt:today(),sales:[],purchases:[],
        }));
        setPrev(parsed); setStep("preview");
      } catch(err) { setError("ファイルの解析に失敗しました。テンプレートに沿ったCSVか確認してください。"); }
    };
    reader.readAsText(file,"UTF-8");
  };
  return (
    <Modal title="案件を一括取込（Excel / CSV）" onClose={onClose} width={620}>
      {step==="upload" && (
        <div style={{display:"flex",flexDirection:"column",gap:16}}>
          <div style={{background:"#F0F4FF",border:"1px solid #C7D2FE",borderRadius:10,padding:"12px 16px",fontSize:12,color:"#4F46E5"}}>
            <div style={{fontWeight:700,marginBottom:6}}>取込手順</div>
            <div style={{lineHeight:1.8}}>1. 「テンプレートをDL」でCSVを取得<br/>2. ExcelやGoogleスプシで案件情報を入力<br/>3. CSV形式で保存してアップロード</div>
          </div>
          <button onClick={dlTemplate} style={{padding:"10px 0",fontSize:13,fontWeight:700,color:"#4F46E5",background:"#EEF2FF",border:"1px solid #C7D2FE",borderRadius:9,cursor:"pointer"}}>📥 テンプレートをダウンロード（CSV）</button>
          <div style={{border:"2px dashed #CBD5E1",borderRadius:12,padding:"32px 20px",textAlign:"center"}} onDragOver={e=>e.preventDefault()} onDrop={e=>{e.preventDefault();handleFile(e.dataTransfer.files[0]);}}>
            <div style={{fontSize:28,marginBottom:8}}>📂</div>
            <div style={{fontSize:13,fontWeight:600,color:"#475569"}}>CSVをドラッグ＆ドロップ</div>
            <button onClick={()=>fileRef.current?.click()} style={{marginTop:10,fontSize:13,color:"#4F46E5",border:"1px solid #C7D2FE",background:"#EEF2FF",borderRadius:8,padding:"8px 20px",cursor:"pointer",fontWeight:600}}>ファイルを選択</button>
            <input ref={fileRef} type="file" accept=".csv" style={{display:"none"}} onChange={e=>handleFile(e.target.files[0])}/>
          </div>
          {error && <div style={{padding:"10px 12px",background:"#FEF2F2",border:"1px solid #FECACA",borderRadius:8,fontSize:12,color:"#DC2626"}}>{error}</div>}
        </div>
      )}
      {step==="preview" && (
        <div style={{display:"flex",flexDirection:"column",gap:14}}>
          <div style={{background:"#D1FAE5",border:"1px solid #A7F3D0",borderRadius:10,padding:"10px 14px",fontSize:12,color:"#065F46",fontWeight:700}}>✓ {preview.length}件のデータを確認してください</div>
          <table style={{width:"100%",borderCollapse:"collapse",fontSize:12}}>
            <thead><tr style={{background:"#F8FAFC",borderBottom:"1px solid #E2E8F0"}}>
              {["案件名","顧客名","担当者","ステータス","通貨"].map(h=><th key={h} style={{padding:"8px 10px",textAlign:"left",fontWeight:700,color:"#64748B"}}>{h}</th>)}
            </tr></thead>
            <tbody>{preview.map((p,i)=>(
              <tr key={i} style={{borderBottom:"1px solid #F1F5F9"}}>
                <td style={{padding:"8px 10px",fontWeight:600,color:"#1E293B"}}>{p.name}</td>
                <td style={{padding:"8px 10px",color:"#475569"}}>{p.client}</td>
                <td style={{padding:"8px 10px",color:"#475569"}}>{p.manager}</td>
                <td style={{padding:"8px 10px"}}><Badge status={p.status}/></td>
                <td style={{padding:"8px 10px"}}><span style={{fontSize:11,fontWeight:700,color:p.currency==="USD"?"#0891B2":"#7C3AED",background:p.currency==="USD"?"#E0F2FE":"#F3E8FF",borderRadius:6,padding:"2px 8px"}}>{p.currency}</span></td>
              </tr>
            ))}</tbody>
          </table>
          <div style={{display:"flex",gap:8}}>
            <button onClick={()=>setStep("upload")} style={{flex:1,padding:"10px 0",fontSize:13,color:"#475569",border:"1px solid #E2E8F0",background:"#fff",borderRadius:9,cursor:"pointer"}}>← 戻る</button>
            <button onClick={()=>{onImport(preview);setStep("done");}} style={{flex:2,padding:"10px 0",fontSize:13,fontWeight:700,color:"#fff",background:"#059669",border:"none",borderRadius:9,cursor:"pointer"}}>✓ {preview.length}件を取込実行</button>
          </div>
        </div>
      )}
      {step==="done" && (
        <div style={{textAlign:"center",padding:"32px 0"}}>
          <div style={{fontSize:40,marginBottom:12}}>✅</div>
          <div style={{fontSize:16,fontWeight:700,color:"#059669",marginBottom:8}}>取込完了！</div>
          <div style={{fontSize:13,color:"#64748B"}}>{preview.length}件を登録しました</div>
          <button onClick={onClose} style={{marginTop:20,padding:"10px 32px",fontSize:13,fontWeight:700,color:"#fff",background:"#4F46E5",border:"none",borderRadius:9,cursor:"pointer"}}>閉じる</button>
        </div>
      )}
    </Modal>
  );
};

// ─────────────────────────────────────────────
// DETAIL PANEL
// ─────────────────────────────────────────────
const DetailPanel = ({project,onClose,onAddSale,onAddPurchase,onDeleteSale,onDeletePurchase,onUpdateStatus,onEdit,onDelete}) => {
  const [tab,setTab] = useState("overview");
  const [confirmDel,setConfirmDel] = useState(false);
  if (!project) return null;
  const st = calcStats(project);
  return (
    <>
      <div style={{position:"fixed",inset:0,zIndex:50}} onClick={onClose}/>
      <div style={{position:"fixed",top:0,right:0,bottom:0,zIndex:60,width:540,background:"#fff",boxShadow:"-8px 0 48px rgba(0,0,0,0.13)",display:"flex",flexDirection:"column"}}>

        <div style={{padding:"16px 20px 12px",borderBottom:"1px solid #F1F5F9"}}>
          <div style={{display:"flex",justifyContent:"space-between",alignItems:"flex-start"}}>
            <div style={{flex:1,minWidth:0}}>
              <div style={{display:"flex",alignItems:"center",gap:8,marginBottom:5}}>
                <span style={{fontSize:10,color:"#94A3B8",fontFamily:"monospace"}}>{project.id}</span>
                <Badge status={project.status}/>
              </div>
              <div style={{fontSize:15,fontWeight:700,color:"#1E293B"}}>{project.name}</div>
              <div style={{fontSize:12,color:"#64748B",marginTop:1}}>{project.client}{project.clientDept?"・"+project.clientDept:""}</div>
            </div>
            <div style={{display:"flex",alignItems:"center",gap:5,flexShrink:0,marginLeft:8}}>
              <button onClick={onEdit} style={{fontSize:11,fontWeight:700,color:"#4F46E5",background:"#EEF2FF",border:"none",borderRadius:7,padding:"5px 10px",cursor:"pointer"}}>✏ 編集</button>
              {!confirmDel
                ? <button onClick={()=>setConfirmDel(true)} style={{fontSize:11,fontWeight:700,color:"#DC2626",background:"#FEF2F2",border:"none",borderRadius:7,padding:"5px 10px",cursor:"pointer"}}>🗑 削除</button>
                : <div style={{display:"flex",alignItems:"center",gap:4}}>
                    <span style={{fontSize:11,color:"#DC2626",fontWeight:700,whiteSpace:"nowrap"}}>本当に削除？</span>
                    <button onClick={()=>{onDelete(project.id);onClose();}} style={{fontSize:11,fontWeight:700,color:"#fff",background:"#DC2626",border:"none",borderRadius:6,padding:"4px 10px",cursor:"pointer"}}>はい</button>
                    <button onClick={()=>setConfirmDel(false)} style={{fontSize:11,color:"#64748B",background:"#F1F5F9",border:"none",borderRadius:6,padding:"4px 8px",cursor:"pointer"}}>戻る</button>
                  </div>
              }
              <button onClick={onClose} style={{background:"#F8FAFC",border:"none",cursor:"pointer",color:"#64748B",width:28,height:28,borderRadius:"50%",fontSize:16,lineHeight:"28px",textAlign:"center"}}>×</button>
            </div>
          </div>
          <div style={{marginTop:10,display:"flex",gap:5,flexWrap:"wrap"}}>
            {Object.entries(STATUS).map(([key,val])=>(
              <button key={key} onClick={()=>onUpdateStatus(project.id,key)}
                style={{fontSize:11,padding:"3px 10px",border:`1px solid ${project.status===key?val.dot:"#E2E8F0"}`,borderRadius:20,cursor:"pointer",fontWeight:project.status===key?700:400,background:project.status===key?val.bg:"#fff",color:project.status===key?val.text:"#94A3B8"}}>
                {val.label}
              </button>
            ))}
          </div>
        </div>

        <div style={{display:"grid",gridTemplateColumns:"repeat(4,1fr)",background:"#F8FAFC",borderBottom:"1px solid #F1F5F9"}}>
          {[{label:"売上",value:fmt(st.salesBase,project.currency),color:"#4F46E5"},{label:"仕入",value:fmt(st.purchBase,project.currency),color:"#334155"},{label:"粗利",value:fmt(st.grossProfit,project.currency),color:st.grossProfit>=0?"#059669":"#DC2626"},{label:"粗利率",value:st.grossMargin.toFixed(1)+"%",color:"#D97706"}].map((m,i)=>(
            <div key={m.label} style={{padding:"10px 12px",borderRight:i<3?"1px solid #F1F5F9":"none"}}>
              <div style={{fontSize:10,color:"#94A3B8",fontWeight:700,textTransform:"uppercase",letterSpacing:0.5,marginBottom:2}}>{m.label}</div>
              <div style={{fontSize:12,fontWeight:700,color:m.color,fontVariantNumeric:"tabular-nums"}}>{m.value}</div>
            </div>
          ))}
        </div>

        <div style={{display:"flex",background:"#fff",borderBottom:"1px solid #F1F5F9"}}>
          {[{id:"overview",label:"概要"},{id:"sales",label:`② 売上 (${project.sales.length})`},{id:"purchases",label:`③ 仕入 (${project.purchases.length})`}].map(t=>(
            <button key={t.id} onClick={()=>setTab(t.id)}
              style={{padding:"10px 18px",fontSize:12,fontWeight:600,border:"none",borderBottom:`2px solid ${tab===t.id?"#4F46E5":"transparent"}`,color:tab===t.id?"#4F46E5":"#64748B",background:"transparent",cursor:"pointer"}}>
              {t.label}
            </button>
          ))}
        </div>

        <div style={{flex:1,overflowY:"auto",padding:"16px 20px"}}>
          {tab==="overview" && (
            <div style={{display:"flex",flexDirection:"column",gap:14}}>
              <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:8}}>
                {[{label:"担当者",value:project.manager||"—"},{label:"カテゴリ",value:project.category||"—"},{label:"開始日",value:project.startDate||"未定"},{label:"完了予定",value:project.endDate||"未定"},{label:"通貨",value:project.currency},{label:"受注確度",value:project.probability+"%"}].map(r=>(
                  <div key={r.label} style={{background:"#F8FAFC",borderRadius:8,padding:"10px 12px"}}>
                    <div style={{fontSize:10,color:"#94A3B8",fontWeight:700,textTransform:"uppercase",letterSpacing:0.5,marginBottom:2}}>{r.label}</div>
                    <div style={{fontSize:13,fontWeight:600,color:"#334155"}}>{r.value}</div>
                  </div>
                ))}
              </div>
              {project.description && <div style={{background:"#F8FAFC",borderRadius:8,padding:"12px 14px",fontSize:13,color:"#475569",lineHeight:1.7}}>{project.description}</div>}
              <div style={{background:"#F0F4FF",border:"1px solid #C7D2FE",borderRadius:12,padding:"14px 16px"}}>
                <div style={{fontSize:11,fontWeight:700,color:"#4F46E5",marginBottom:12,textTransform:"uppercase"}}>粗利内訳</div>
                {[{label:"売上合計（税抜）",value:fmt(st.salesBase,project.currency),color:"#334155",bold:true},{label:"　消費税",value:fmt(st.salesTax,project.currency),color:"#7C3AED",small:true},{label:"仕入合計（税抜）",value:"− "+fmt(st.purchBase,project.currency),color:"#DC2626",bold:true,sep:true},{label:"　仮払消費税",value:fmt(st.purchTax,project.currency),color:"#94A3B8",small:true}].map((r,i)=>(
                  <div key={i} style={{display:"flex",justifyContent:"space-between",padding:r.sep?"8px 0 3px":"3px 0",borderTop:r.sep?"1px solid #C7D2FE":"none",marginTop:r.sep?4:0}}>
                    <span style={{fontSize:r.small?11:12,color:r.small?"#94A3B8":"#64748B"}}>{r.label}</span>
                    <span style={{fontSize:r.small?11:12,fontWeight:r.bold?700:400,color:r.color,fontVariantNumeric:"tabular-nums"}}>{r.value}</span>
                  </div>
                ))}
                <div style={{display:"flex",justifyContent:"space-between",padding:"10px 0 4px",borderTop:"2px solid #A5B4FC",marginTop:8}}>
                  <span style={{fontSize:14,fontWeight:700,color:"#4F46E5"}}>粗利</span>
                  <div>
                    <span style={{fontSize:18,fontWeight:700,color:st.grossProfit>=0?"#059669":"#DC2626",fontVariantNumeric:"tabular-nums"}}>{fmt(st.grossProfit,project.currency)}</span>
                    <span style={{fontSize:12,color:"#64748B",marginLeft:8}}>{st.grossMargin.toFixed(1)}%</span>
                  </div>
                </div>
              </div>
              <div style={{display:"flex",gap:8}}>
                <button onClick={()=>setTab("sales")} style={{flex:1,padding:"10px 0",fontSize:12,fontWeight:700,color:"#4F46E5",background:"#EEF2FF",border:"none",borderRadius:8,cursor:"pointer"}}>② 売上明細を入力</button>
                <button onClick={()=>setTab("purchases")} style={{flex:1,padding:"10px 0",fontSize:12,fontWeight:700,color:"#DC2626",background:"#FEF2F2",border:"none",borderRadius:8,cursor:"pointer"}}>③ 仕入明細を入力</button>
              </div>
            </div>
          )}

          {tab==="sales" && (
            <div style={{display:"flex",flexDirection:"column",gap:10}}>
              <div style={{display:"flex",justifyContent:"space-between",alignItems:"center"}}>
                <span style={{fontSize:12,color:"#64748B",fontWeight:700}}>売上明細 — {project.sales.length}件</span>
                <button onClick={onAddSale} style={{fontSize:12,fontWeight:700,color:"#fff",background:"#4F46E5",border:"none",borderRadius:8,padding:"7px 14px",cursor:"pointer"}}>＋ 売上を追加</button>
              </div>
              {project.sales.length===0
                ? <div style={{textAlign:"center",padding:"40px 0",color:"#94A3B8",fontSize:13}}>売上明細がありません</div>
                : project.sales.map(s=>{
                    const base = s.taxType==="internal"?Math.round(s.amount/(1+s.taxRate/100)):s.amount;
                    return (
                      <div key={s.id} style={{border:"1px solid #E2E8F0",borderRadius:10,padding:"12px 14px",position:"relative"}}>
                        <button onClick={()=>onDeleteSale(project.id,s.id)} style={{position:"absolute",top:10,right:10,background:"none",border:"none",color:"#CBD5E1",cursor:"pointer",fontSize:14}}>×</button>
                        <div style={{display:"flex",justifyContent:"space-between",paddingRight:20}}>
                          <div>
                            <div style={{fontSize:13,fontWeight:600,color:"#1E293B"}}>{s.desc}</div>
                            {s.invoiceNo && <div style={{fontSize:11,color:"#94A3B8",fontFamily:"monospace",marginTop:2}}>{s.invoiceNo}</div>}
                          </div>
                          <div style={{textAlign:"right"}}>
                            <div style={{fontSize:14,fontWeight:700,color:"#334155",fontVariantNumeric:"tabular-nums"}}>{fmt(base,project.currency)}</div>
                            <div style={{fontSize:11,color:"#7C3AED"}}>{s.taxType==="none"?"非課税":s.taxType==="internal"?`内税${s.taxRate}%`:`外税${s.taxRate}%`}</div>
                          </div>
                        </div>
                        <div style={{display:"flex",gap:14,marginTop:8,fontSize:11,color:"#64748B"}}>
                          <span>請求: {s.invoiceDate||"—"}</span>
                          <span>入金期日: {s.dueDate||"—"}</span>
                          <span style={{fontWeight:700,color:s.paid?"#059669":"#D97706"}}>{s.paid?"✓ 入金済":"● 未入金"}</span>
                        </div>
                      </div>
                    );
                  })
              }
              {project.sales.length>0 && (
                <div style={{background:"#EEF2FF",borderRadius:10,padding:"12px 14px"}}>
                  <div style={{display:"flex",justifyContent:"space-between",fontSize:13,fontWeight:700,color:"#4F46E5"}}><span>合計（税抜）</span><span>{fmt(st.salesBase,project.currency)}</span></div>
                  <div style={{display:"flex",justifyContent:"space-between",fontSize:11,color:"#059669",marginTop:5}}><span>入金済</span><span>{fmt(st.collectedSales,project.currency)}</span></div>
                  <div style={{display:"flex",justifyContent:"space-between",fontSize:11,color:"#D97706",marginTop:3}}><span>未入金残</span><span>{fmt(st.salesBase-st.collectedSales,project.currency)}</span></div>
                </div>
              )}
            </div>
          )}

          {tab==="purchases" && (
            <div style={{display:"flex",flexDirection:"column",gap:10}}>
              <div style={{display:"flex",justifyContent:"space-between",alignItems:"center"}}>
                <span style={{fontSize:12,color:"#64748B",fontWeight:700}}>仕入明細 — {project.purchases.length}件</span>
                <button onClick={onAddPurchase} style={{fontSize:12,fontWeight:700,color:"#fff",background:"#DC2626",border:"none",borderRadius:8,padding:"7px 14px",cursor:"pointer"}}>＋ 仕入を追加</button>
              </div>
              {project.purchases.length===0
                ? <div style={{textAlign:"center",padding:"40px 0",color:"#94A3B8",fontSize:13}}>仕入明細がありません</div>
                : project.purchases.map(p=>{
                    const base = p.taxType==="internal"?Math.round(p.amount/(1+p.taxRate/100)):p.amount;
                    return (
                      <div key={p.id} style={{border:"1px solid #E2E8F0",borderRadius:10,padding:"12px 14px",position:"relative"}}>
                        <button onClick={()=>onDeletePurchase(project.id,p.id)} style={{position:"absolute",top:10,right:10,background:"none",border:"none",color:"#CBD5E1",cursor:"pointer",fontSize:14}}>×</button>
                        <div style={{display:"flex",justifyContent:"space-between",paddingRight:20}}>
                          <div>
                            <div style={{fontSize:13,fontWeight:600,color:"#1E293B"}}>{p.desc}</div>
                            {p.supplier && <div style={{fontSize:11,color:"#94A3B8",marginTop:2}}>仕入先: {p.supplier}</div>}
                          </div>
                          <div style={{textAlign:"right"}}>
                            <div style={{fontSize:14,fontWeight:700,color:"#DC2626",fontVariantNumeric:"tabular-nums"}}>{fmt(base,project.currency)}</div>
                            <div style={{fontSize:11,color:"#7C3AED"}}>{p.taxType==="none"?"非課税":p.taxType==="internal"?`内税${p.taxRate}%`:`外税${p.taxRate}%`}</div>
                          </div>
                        </div>
                        <div style={{display:"flex",gap:14,marginTop:8,fontSize:11,color:"#64748B"}}>
                          <span>支払期日: {p.dueDate||"—"}</span>
                          <span style={{fontWeight:700,color:p.paid?"#059669":"#D97706"}}>{p.paid?"✓ 支払済":"● 未払"}</span>
                        </div>
                      </div>
                    );
                  })
              }
              {project.purchases.length>0 && (
                <div style={{background:"#FEF2F2",borderRadius:10,padding:"12px 14px"}}>
                  <div style={{display:"flex",justifyContent:"space-between",fontSize:13,fontWeight:700,color:"#DC2626"}}><span>合計（税抜）</span><span>{fmt(st.purchBase,project.currency)}</span></div>
                  <div style={{display:"flex",justifyContent:"space-between",fontSize:11,color:"#059669",marginTop:5}}><span>支払済</span><span>{fmt(st.paidPurch,project.currency)}</span></div>
                  <div style={{display:"flex",justifyContent:"space-between",fontSize:11,color:"#D97706",marginTop:3}}><span>未払残</span><span>{fmt(st.purchBase-st.paidPurch,project.currency)}</span></div>
                </div>
              )}
            </div>
          )}
        </div>
      </div>
    </>
  );
};

// ─────────────────────────────────────────────
// SETTINGS
// ─────────────────────────────────────────────
const SettingsView = ({goals,setGoals,users,setUsers,loginHistory,currentUser}) => {
  const [tab,setTab] = useState("goals");
  const [gf,setGf]   = useState({sales:goals.sales/10000,gp:goals.grossProfit/10000});
  const [saved,setSaved] = useState(false);
  const [nu,setNu]   = useState({name:"",email:"",role:"user",password:""});
  const [umsg,setUmsg]= useState("");
  const isAdmin = currentUser.role==="admin";
  const saveGoals = () => { setGoals({sales:gf.sales*10000,grossProfit:gf.gp*10000}); setSaved(true); setTimeout(()=>setSaved(false),2000); };
  const addUser = () => {
    if (!nu.name||!nu.email||!nu.password){setUmsg("必須項目を入力してください");return;}
    if (users.find(u=>u.email===nu.email)){setUmsg("このメールアドレスは既に登録されています");return;}
    setUsers(us=>[...us,{id:uid(),...nu,locked:false,createdAt:today()}]);
    setNu({name:"",email:"",role:"user",password:""});
    setUmsg("✓ ユーザーを追加しました"); setTimeout(()=>setUmsg(""),2000);
  };
  const toggleLock = (id) => setUsers(us=>us.map(u=>u.id===id?{...u,locked:!u.locked}:u));
  return (
    <div style={{display:"flex",flexDirection:"column",gap:0}}>
      <div style={{display:"flex",borderBottom:"1px solid #F1F5F9",marginBottom:20}}>
        {[{id:"goals",label:"目標値設定"},{id:"users",label:"ユーザー管理"},{id:"history",label:"ログイン履歴"},{id:"lock",label:"ロック管理"}].map(t=>(
          <button key={t.id} onClick={()=>setTab(t.id)}
            style={{padding:"10px 20px",fontSize:13,fontWeight:600,border:"none",borderBottom:`2px solid ${tab===t.id?"#4F46E5":"transparent"}`,color:tab===t.id?"#4F46E5":"#64748B",background:"transparent",cursor:"pointer"}}>
            {t.label}
          </button>
        ))}
      </div>

      {tab==="goals" && (
        <div style={{maxWidth:480,display:"flex",flexDirection:"column",gap:18}}>
          {!isAdmin && <div style={{padding:"10px 14px",background:"#FEF3C7",border:"1px solid #FDE68A",borderRadius:9,fontSize:12,color:"#92400E",fontWeight:600}}>⚠ 目標値の変更は管理者のみ可能です</div>}
          {[{label:"年間売上目標（万円）",key:"sales",color:"#4F46E5"},{label:"年間粗利目標（万円）",key:"gp",color:"#059669"}].map(r=>(
            <div key={r.key} style={{background:"#fff",border:"1px solid #F1F5F9",borderRadius:12,padding:"18px 20px"}}>
              <Lbl>{r.label}</Lbl>
              <div style={{display:"flex",alignItems:"center",gap:10,marginBottom:8}}>
                <span style={{fontSize:13,color:"#64748B"}}>¥</span>
                <input type="number" min={0} style={{...inp,fontSize:20,fontWeight:700,color:r.color}} value={gf[r.key]} onChange={e=>setGf(f=>({...f,[r.key]:Number(e.target.value)}))} disabled={!isAdmin}/>
                <span style={{fontSize:13,color:"#94A3B8",whiteSpace:"nowrap"}}>万円</span>
              </div>
              <div style={{fontSize:12,color:"#94A3B8"}}>= ¥{(gf[r.key]*10000).toLocaleString("ja-JP")}</div>
            </div>
          ))}
          {isAdmin && <button onClick={saveGoals} style={{padding:"12px 0",fontSize:14,fontWeight:700,color:"#fff",background:saved?"#059669":"#4F46E5",border:"none",borderRadius:10,cursor:"pointer"}}>{saved?"✓ 保存しました":"目標値を保存する"}</button>}
        </div>
      )}

      {tab==="users" && (
        <div style={{display:"flex",flexDirection:"column",gap:16}}>
          {isAdmin && (
            <div style={{background:"#fff",border:"1px solid #F1F5F9",borderRadius:12,padding:"18px 20px"}}>
              <div style={{fontSize:13,fontWeight:700,color:"#1E293B",marginBottom:14}}>新規ユーザー追加</div>
              <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:12}}>
                <Field label="氏名" required><input style={inp} value={nu.name} onChange={e=>setNu(u=>({...u,name:e.target.value}))} placeholder="田中 太郎"/></Field>
                <Field label="メールアドレス" required><input style={inp} value={nu.email} onChange={e=>setNu(u=>({...u,email:e.target.value}))} placeholder="tanaka@company.com"/></Field>
                <Field label="権限"><select style={inp} value={nu.role} onChange={e=>setNu(u=>({...u,role:e.target.value}))}><option value="user">一般ユーザー</option><option value="admin">管理者</option></select></Field>
                <Field label="パスワード" required><input type="password" style={inp} value={nu.password} onChange={e=>setNu(u=>({...u,password:e.target.value}))} placeholder="初期パスワード"/></Field>
              </div>
              {umsg && <div style={{marginTop:10,fontSize:12,color:umsg.startsWith("✓")?"#059669":"#DC2626",fontWeight:600}}>{umsg}</div>}
              <button onClick={addUser} style={{marginTop:14,padding:"9px 24px",fontSize:13,fontWeight:700,color:"#fff",background:"#4F46E5",border:"none",borderRadius:9,cursor:"pointer"}}>＋ ユーザーを追加</button>
            </div>
          )}
          <div style={{background:"#fff",border:"1px solid #F1F5F9",borderRadius:12,overflow:"hidden"}}>
            <div style={{padding:"12px 18px",borderBottom:"1px solid #F8FAFC",fontSize:11,fontWeight:700,color:"#64748B",textTransform:"uppercase"}}>登録ユーザー一覧 ({users.length}名)</div>
            <table style={{width:"100%",borderCollapse:"collapse"}}>
              <thead><tr style={{background:"#F8FAFC"}}>{["氏名","メール","権限","状態","登録日"].map(h=><th key={h} style={{padding:"8px 14px",fontSize:11,color:"#94A3B8",fontWeight:700,textAlign:"left"}}>{h}</th>)}</tr></thead>
              <tbody>{users.map(u=>(
                <tr key={u.id} style={{borderTop:"1px solid #F8FAFC"}}>
                  <td style={{padding:"10px 14px",fontSize:13,fontWeight:600,color:"#1E293B"}}>{u.name}</td>
                  <td style={{padding:"10px 14px",fontSize:12,color:"#64748B"}}>{u.email}</td>
                  <td style={{padding:"10px 14px"}}><span style={{fontSize:11,fontWeight:700,color:u.role==="admin"?"#7C3AED":"#475569",background:u.role==="admin"?"#F3E8FF":"#F1F5F9",borderRadius:20,padding:"3px 10px"}}>{u.role==="admin"?"管理者":"一般"}</span></td>
                  <td style={{padding:"10px 14px"}}><span style={{fontSize:11,fontWeight:700,color:u.locked?"#DC2626":"#059669",background:u.locked?"#FEF2F2":"#D1FAE5",borderRadius:20,padding:"3px 10px"}}>{u.locked?"🔒 ロック中":"✓ 有効"}</span></td>
                  <td style={{padding:"10px 14px",fontSize:12,color:"#94A3B8"}}>{u.createdAt}</td>
                </tr>
              ))}</tbody>
            </table>
          </div>
        </div>
      )}

      {tab==="history" && (
        <div style={{background:"#fff",border:"1px solid #F1F5F9",borderRadius:12,overflow:"hidden"}}>
          <div style={{padding:"12px 18px",borderBottom:"1px solid #F8FAFC",fontSize:11,fontWeight:700,color:"#64748B",textTransform:"uppercase"}}>ログイン履歴（{loginHistory.length}件）</div>
          <table style={{width:"100%",borderCollapse:"collapse"}}>
            <thead><tr style={{background:"#F8FAFC"}}>{["日時","氏名","メール","結果","IP"].map(h=><th key={h} style={{padding:"8px 14px",fontSize:11,color:"#94A3B8",fontWeight:700,textAlign:"left"}}>{h}</th>)}</tr></thead>
            <tbody>{loginHistory.map(h=>{
              const rs = h.result==="success"?{bg:"#D1FAE5",text:"#065F46",label:"✓ 成功"}:h.result==="locked"?{bg:"#FEF2F2",text:"#DC2626",label:"🔒 ロック"}:{bg:"#FEF3C7",text:"#92400E",label:"✗ 失敗"};
              return (
                <tr key={h.id} style={{borderTop:"1px solid #F8FAFC"}}>
                  <td style={{padding:"9px 14px",fontSize:12,color:"#475569",fontFamily:"monospace"}}>{h.at}</td>
                  <td style={{padding:"9px 14px",fontSize:13,fontWeight:600,color:"#1E293B"}}>{h.name}</td>
                  <td style={{padding:"9px 14px",fontSize:12,color:"#64748B"}}>{h.email}</td>
                  <td style={{padding:"9px 14px"}}><span style={{fontSize:11,fontWeight:700,background:rs.bg,color:rs.text,borderRadius:20,padding:"3px 10px"}}>{rs.label}</span></td>
                  <td style={{padding:"9px 14px",fontSize:12,color:"#94A3B8",fontFamily:"monospace"}}>{h.ip}</td>
                </tr>
              );
            })}</tbody>
          </table>
        </div>
      )}

      {tab==="lock" && (
        <div style={{display:"flex",flexDirection:"column",gap:12}}>
          {!isAdmin && <div style={{padding:"10px 14px",background:"#FEF3C7",border:"1px solid #FDE68A",borderRadius:9,fontSize:12,color:"#92400E",fontWeight:600}}>⚠ ロックの操作は管理者のみ可能です</div>}
          {users.filter(u=>u.id!==currentUser.id).map(u=>(
            <div key={u.id} style={{background:"#fff",border:`1px solid ${u.locked?"#FECACA":"#F1F5F9"}`,borderRadius:12,padding:"16px 18px",display:"flex",alignItems:"center",gap:16}}>
              <div style={{width:40,height:40,borderRadius:"50%",background:u.locked?"#FEF2F2":"#EEF2FF",display:"flex",alignItems:"center",justifyContent:"center",fontSize:14,fontWeight:700,color:u.locked?"#DC2626":"#4F46E5",flexShrink:0}}>{u.name.charAt(0)}</div>
              <div style={{flex:1}}>
                <div style={{fontSize:13,fontWeight:700,color:"#1E293B"}}>{u.name}</div>
                <div style={{fontSize:11,color:"#94A3B8",marginTop:2}}>{u.email} · {u.role==="admin"?"管理者":"一般"}</div>
                {u.locked && <div style={{fontSize:11,color:"#DC2626",marginTop:4,fontWeight:600}}>🔒 ログインがロックされています</div>}
              </div>
              {isAdmin && (
                <button onClick={()=>toggleLock(u.id)} style={{padding:"8px 16px",fontSize:12,fontWeight:700,color:"#fff",background:u.locked?"#059669":"#DC2626",border:"none",borderRadius:8,cursor:"pointer",whiteSpace:"nowrap"}}>
                  {u.locked?"🔓 ロック解除":"🔒 ロック"}
                </button>
              )}
            </div>
          ))}
        </div>
      )}
    </div>
  );
};

// ─────────────────────────────────────────────
// PROJECT LIST VIEW
// ─────────────────────────────────────────────
const ProjectListView = ({projects,onSelectProject,onNewProject,onExportCSV,onImport}) => {
  const [search,setSearch]   = useState("");
  const [fStatus,setFStatus] = useState("all");
  const [fCurr,setFCurr]     = useState("all");
  const [sortBy,setSortBy]   = useState("createdAt");
  const [sortDir,setSortDir] = useState("desc");

  const filtered = useMemo(()=>{
    let list = [...projects];
    if (fStatus!=="all") list = list.filter(p=>p.status===fStatus);
    if (fCurr!=="all")   list = list.filter(p=>p.currency===fCurr);
    if (search) {
      const q = search.toLowerCase();
      list = list.filter(p=>p.name.toLowerCase().includes(q)||p.client.toLowerCase().includes(q)||p.id.toLowerCase().includes(q)||(p.manager||"").toLowerCase().includes(q));
    }
    list.sort((a,b)=>{
      const va = sortBy==="sales"?calcStats(a).salesBase:sortBy==="grossProfit"?calcStats(a).grossProfit:a[sortBy]??"";
      const vb = sortBy==="sales"?calcStats(b).salesBase:sortBy==="grossProfit"?calcStats(b).grossProfit:b[sortBy]??"";
      if (va<vb) return sortDir==="asc"?-1:1;
      if (va>vb) return sortDir==="asc"?1:-1;
      return 0;
    });
    return list;
  },[projects,search,fStatus,fCurr,sortBy,sortDir]);

  const toggleSort = (col) => { if(sortBy===col) setSortDir(d=>d==="asc"?"desc":"asc"); else{setSortBy(col);setSortDir("desc");} };
  const SortIco = ({col}) => sortBy!==col
    ? <span style={{color:"#CBD5E1",marginLeft:3,fontSize:10}}>↕</span>
    : <span style={{color:"#4F46E5",marginLeft:3,fontSize:10}}>{sortDir==="asc"?"↑":"↓"}</span>;
  const Th = ({col,children,align="left"}) => (
    <th onClick={()=>toggleSort(col)} style={{padding:"10px 12px",fontSize:11,fontWeight:700,color:"#64748B",textAlign:align,cursor:"pointer",whiteSpace:"nowrap",background:"#F8FAFC",userSelect:"none",textTransform:"uppercase",letterSpacing:0.5}}>
      {children}<SortIco col={col}/>
    </th>
  );

  return (
    <div style={{display:"flex",flexDirection:"column",gap:14}}>
      <div style={{display:"flex",alignItems:"center",gap:8}}>
        <div style={{flex:1,position:"relative"}}>
          <span style={{position:"absolute",left:10,top:"50%",transform:"translateY(-50%)",color:"#94A3B8",fontSize:13}}>🔍</span>
          <input value={search} onChange={e=>setSearch(e.target.value)} placeholder="案件名・顧客名・担当者・IDで検索..." style={{...inp,paddingLeft:30}}/>
        </div>
        <select value={fStatus} onChange={e=>setFStatus(e.target.value)} style={{...inp,width:120}}>
          <option value="all">全ステータス</option>
          {Object.entries(STATUS).map(([k,v])=><option key={k} value={k}>{v.label}</option>)}
        </select>
        <select value={fCurr} onChange={e=>setFCurr(e.target.value)} style={{...inp,width:90}}>
          <option value="all">全通貨</option><option value="JPY">JPY</option><option value="USD">USD</option>
        </select>
        <button onClick={onExportCSV} style={{padding:"8px 14px",fontSize:12,fontWeight:600,color:"#475569",border:"1px solid #E2E8F0",borderRadius:8,background:"#fff",cursor:"pointer",whiteSpace:"nowrap"}}>📄 CSV出力</button>
        <button onClick={onImport} style={{padding:"8px 14px",fontSize:12,fontWeight:600,color:"#059669",border:"1px solid #A7F3D0",background:"#D1FAE5",borderRadius:8,cursor:"pointer",whiteSpace:"nowrap"}}>📥 Excel取込</button>
        <button onClick={onNewProject} style={{padding:"8px 16px",fontSize:12,fontWeight:700,color:"#fff",background:"#4F46E5",border:"none",borderRadius:8,cursor:"pointer",whiteSpace:"nowrap"}}>＋ 新規案件</button>
      </div>
      <div style={{background:"#fff",borderRadius:12,border:"1px solid #F1F5F9",overflow:"hidden"}}>
        <table style={{width:"100%",borderCollapse:"collapse"}}>
          <thead>
            <tr style={{borderBottom:"2px solid #F1F5F9"}}>
              <Th col="id">案件ID</Th>
              <Th col="name">案件名</Th>
              <Th col="client">顧客</Th>
              <Th col="status">ステータス</Th>
              <Th col="manager">担当</Th>
              <Th col="currency">通貨</Th>
              <Th col="sales" align="right">売上（税抜）</Th>
              <Th col="grossProfit" align="right">粗利</Th>
              <Th col="endDate">完了予定</Th>
              <th style={{padding:"10px 12px",background:"#F8FAFC",width:60}}></th>
            </tr>
          </thead>
          <tbody>
            {filtered.map((p,i)=>{
              const st = calcStats(p);
              return (
                <tr key={p.id} onClick={()=>onSelectProject(p.id)}
                  style={{borderBottom:"1px solid #F8FAFC",background:i%2===0?"#fff":"#FAFAFA",cursor:"pointer"}}
                  onMouseEnter={e=>e.currentTarget.style.background="#F0F4FF"}
                  onMouseLeave={e=>e.currentTarget.style.background=i%2===0?"#fff":"#FAFAFA"}>
                  <td style={{padding:"10px 12px",fontSize:11,color:"#94A3B8",fontFamily:"monospace"}}>{p.id}</td>
                  <td style={{padding:"10px 12px"}}>
                    <div style={{fontSize:13,fontWeight:600,color:"#1E293B"}}>{p.name}</div>
                    <div style={{fontSize:11,color:"#94A3B8",marginTop:1}}>{p.category}</div>
                  </td>
                  <td style={{padding:"10px 12px",fontSize:12,color:"#475569"}}>{p.client}</td>
                  <td style={{padding:"10px 12px"}}><Badge status={p.status}/></td>
                  <td style={{padding:"10px 12px",fontSize:12,color:"#475569"}}>{p.manager}</td>
                  <td style={{padding:"10px 12px"}}>
                    <span style={{fontSize:11,fontWeight:700,color:p.currency==="USD"?"#0891B2":"#7C3AED",background:p.currency==="USD"?"#E0F2FE":"#F3E8FF",borderRadius:6,padding:"2px 8px"}}>{p.currency}</span>
                  </td>
                  <td style={{padding:"10px 12px",textAlign:"right",fontSize:13,fontWeight:700,color:"#334155",fontVariantNumeric:"tabular-nums"}}>
                    {st.salesBase>0?fmt(st.salesBase,p.currency):<span style={{color:"#CBD5E1"}}>未入力</span>}
                  </td>
                  <td style={{padding:"10px 12px",textAlign:"right"}}>
                    <div style={{fontSize:13,fontWeight:700,color:st.grossProfit>=0?"#059669":"#DC2626",fontVariantNumeric:"tabular-nums"}}>
                      {st.salesBase>0?fmt(st.grossProfit,p.currency):<span style={{color:"#CBD5E1"}}>—</span>}
                    </div>
                    {st.salesBase>0 && <div style={{fontSize:11,color:"#94A3B8"}}>{st.grossMargin.toFixed(1)}%</div>}
                  </td>
                  <td style={{padding:"10px 12px",fontSize:12,color:"#94A3B8"}}>{p.endDate||"—"}</td>
                  <td style={{padding:"10px 12px",textAlign:"center"}}><span style={{fontSize:12,color:"#4F46E5",fontWeight:600}}>詳細 →</span></td>
                </tr>
              );
            })}
            {filtered.length===0 && (
              <tr><td colSpan={10} style={{padding:"40px 0",textAlign:"center",color:"#94A3B8",fontSize:13}}>該当する案件がありません</td></tr>
            )}
          </tbody>
        </table>
      </div>
      <div style={{fontSize:11,color:"#94A3B8"}}>{filtered.length}件 / 全{projects.length}件表示</div>
    </div>
  );
};

// ─────────────────────────────────────────────
// DASHBOARD
// ─────────────────────────────────────────────
const Dashboard = ({projects,goals,onSelectProject}) => {
  const jpyProjs = useMemo(()=>projects.filter(p=>p.status!=="lost"&&p.currency==="JPY"),[projects]);
  const totalSales   = jpyProjs.reduce((s,p)=>s+calcStats(p).salesBase,0);
  const totalPurch   = jpyProjs.reduce((s,p)=>s+calcStats(p).purchBase,0);
  const grossProfit  = totalSales - totalPurch;
  const margin       = totalSales>0 ? grossProfit/totalSales*100 : 0;
  const uncollected  = jpyProjs.reduce((s,p)=>{ const st=calcStats(p); return s+(st.salesBase-st.collectedSales); },0);
  const unpaid       = jpyProjs.reduce((s,p)=>{ const st=calcStats(p); return s+(st.purchBase-st.paidPurch); },0);
  const activeCount  = projects.filter(p=>["inProgress","ordered"].includes(p.status)).length;
  const pipelineData = Object.entries(STATUS).map(([key])=>({key,count:projects.filter(p=>p.status===key).length,amount:projects.filter(p=>p.status===key).reduce((s,p)=>s+calcStats(p).salesBase,0)}));

  const managerStats = useMemo(()=>{
    const map={};
    jpyProjs.forEach(p=>{
      const name = p.manager||"未設定";
      if (!map[name]) map[name]={name,sales:0,grossProfit:0,count:0};
      const st = calcStats(p);
      map[name].sales += st.salesBase;
      map[name].grossProfit += st.grossProfit;
      map[name].count += 1;
    });
    return Object.values(map).sort((a,b)=>b.sales-a.sales);
  },[jpyProjs]);

  const mSalesGoal = goals.sales / Math.max(managerStats.length,1);
  const mGpGoal    = goals.grossProfit / Math.max(managerStats.length,1);

  return (
    <div style={{display:"flex",flexDirection:"column",gap:20}}>

      <div style={{display:"grid",gridTemplateColumns:"1fr 1fr",gap:12}}>
        <GoalCard label="売上目標達成率（JPY・税抜）" actual={totalSales} target={goals.sales} color="#4F46E5"/>
        <GoalCard label="粗利目標達成率（JPY）" actual={Math.max(grossProfit,0)} target={goals.grossProfit} color="#059669"/>
      </div>

      <div style={{display:"grid",gridTemplateColumns:"repeat(3,1fr)",gap:12}}>
        {[{label:"総売上（JPY・税抜）",value:fmt(totalSales),color:"#4F46E5",sub:`進行中 ${activeCount}件`},{label:"粗利（JPY）",value:fmt(grossProfit),color:grossProfit>=0?"#059669":"#DC2626",sub:`粗利率 ${margin.toFixed(1)}%`},{label:"未入金残高",value:fmt(uncollected),color:"#D97706",sub:`未払残 ${fmt(unpaid)}`}].map(m=>(
          <div key={m.label} style={{background:"#fff",border:"1px solid #F1F5F9",borderRadius:12,padding:"14px 16px"}}>
            <div style={{fontSize:11,color:"#94A3B8",fontWeight:700,textTransform:"uppercase",letterSpacing:0.5,marginBottom:5}}>{m.label}</div>
            <div style={{fontSize:22,fontWeight:800,color:m.color,fontVariantNumeric:"tabular-nums",letterSpacing:-0.5}}>{m.value}</div>
            <div style={{fontSize:11,color:"#94A3B8",marginTop:3}}>{m.sub}</div>
          </div>
        ))}
      </div>

      {managerStats.length>0 && (
        <div style={{background:"#fff",border:"1px solid #F1F5F9",borderRadius:12,padding:"18px 20px"}}>
          <div style={{display:"flex",alignItems:"baseline",justifyContent:"space-between",marginBottom:16}}>
            <div style={{fontSize:11,fontWeight:700,color:"#64748B",textTransform:"uppercase",letterSpacing:0.5}}>担当者別 達成率</div>
            <div style={{fontSize:11,color:"#94A3B8"}}>目標を担当者数で均等配分 / 失注除く・JPYのみ</div>
          </div>
          <div style={{display:"flex",flexDirection:"column",gap:14}}>
            {managerStats.map((m,i)=>{
              const color   = MANAGER_COLORS[i%MANAGER_COLORS.length];
              const sPct    = mSalesGoal>0 ? Math.min(m.sales/mSalesGoal*100,100) : 0;
              const gPct    = mGpGoal>0   ? Math.min(m.grossProfit/mGpGoal*100,100) : 0;
              const gpColor = m.grossProfit>=0?"#059669":"#DC2626";
              return (
                <div key={m.name} style={{display:"grid",gridTemplateColumns:"120px 1fr 1fr",gap:16,alignItems:"center",padding:"12px 14px",background:"#F8FAFC",borderRadius:10,borderLeft:`3px solid ${color}`}}>
                  <div>
                    <div style={{fontSize:13,fontWeight:700,color:"#1E293B"}}>{m.name}</div>
                    <div style={{fontSize:11,color:"#94A3B8",marginTop:2}}>{m.count}件担当</div>
                  </div>
                  <div>
                    <div style={{display:"flex",justifyContent:"space-between",marginBottom:5}}>
                      <span style={{fontSize:11,color:"#64748B",fontWeight:600}}>売上</span>
                      <span style={{fontSize:12,fontWeight:700,color,fontVariantNumeric:"tabular-nums"}}>{fmt(m.sales)}</span>
                    </div>
                    <div style={{height:8,background:"#E2E8F0",borderRadius:4,overflow:"hidden"}}>
                      <div style={{height:"100%",width:`${Math.max(sPct,sPct>0?2:0)}%`,background:color,borderRadius:4}}/>
                    </div>
                    <div style={{display:"flex",justifyContent:"space-between",marginTop:3,fontSize:10,color:"#94A3B8"}}>
                      <span>0</span>
                      <span style={{fontWeight:600,color}}>{Math.round(sPct)}% 達成</span>
                      <span>¥{fmtMan(mSalesGoal)}</span>
                    </div>
                  </div>
                  <div>
                    <div style={{display:"flex",justifyContent:"space-between",marginBottom:5}}>
                      <span style={{fontSize:11,color:"#64748B",fontWeight:600}}>粗利</span>
                      <span style={{fontSize:12,fontWeight:700,color:gpColor,fontVariantNumeric:"tabular-nums"}}>{fmt(m.grossProfit)}</span>
                    </div>
                    <div style={{height:8,background:"#E2E8F0",borderRadius:4,overflow:"hidden"}}>
                      <div style={{height:"100%",width:`${Math.max(gPct,gPct>0?2:0)}%`,background:gpColor,borderRadius:4}}/>
                    </div>
                    <div style={{display:"flex",justifyContent:"space-between",marginTop:3,fontSize:10,color:"#94A3B8"}}>
                      <span>0</span>
                      <span style={{fontWeight:600,color:gpColor}}>{Math.round(gPct)}% 達成</span>
                      <span>¥{fmtMan(mGpGoal)}</span>
                    </div>
                  </div>
                </div>
              );
            })}
          </div>
          <div style={{marginTop:10,fontSize:11,color:"#CBD5E1"}}>※ 担当者個別目標の設定は設定画面で対応予定</div>
        </div>
      )}

      <div style={{display:"grid",gridTemplateColumns:"220px 1fr",gap:14}}>
        <div style={{background:"#fff",border:"1px solid #F1F5F9",borderRadius:12,padding:"16px 18px"}}>
          <div style={{fontSize:11,fontWeight:700,color:"#64748B",textTransform:"uppercase",letterSpacing:0.5,marginBottom:14}}>案件パイプライン</div>
          <div style={{display:"flex",flexDirection:"column",gap:10}}>
            {pipelineData.map(({key,count,amount})=>(
              <div key={key} style={{display:"flex",alignItems:"center",justifyContent:"space-between"}}>
                <div style={{display:"flex",alignItems:"center",gap:8}}><Badge status={key}/><span style={{fontSize:12,color:"#94A3B8"}}>{count}件</span></div>
                <span style={{fontSize:12,fontWeight:700,color:"#475569",fontVariantNumeric:"tabular-nums"}}>{amount>0?fmt(amount):"—"}</span>
              </div>
            ))}
          </div>
        </div>
        <div style={{background:"#fff",border:"1px solid #F1F5F9",borderRadius:12,overflow:"hidden"}}>
          <div style={{padding:"14px 18px",borderBottom:"1px solid #F8FAFC",fontSize:11,fontWeight:700,color:"#64748B",textTransform:"uppercase"}}>案件一覧（{projects.length}件）</div>
          <table style={{width:"100%",borderCollapse:"collapse"}}>
            <thead><tr style={{background:"#F8FAFC",borderBottom:"1px solid #F1F5F9"}}>
              {["案件名","顧客","ステータス","売上（税抜）","粗利","粗利率"].map(h=><th key={h} style={{padding:"8px 12px",fontSize:11,color:"#94A3B8",fontWeight:700,textAlign:"left"}}>{h}</th>)}
            </tr></thead>
            <tbody>
              {projects.length===0
                ? <tr><td colSpan={6} style={{padding:"40px 0",textAlign:"center",color:"#CBD5E1",fontSize:13}}>案件がありません。「＋ 新規案件」から登録してください。</td></tr>
                : projects.map(p=>{
                    const st=calcStats(p);
                    return (
                      <tr key={p.id} onClick={()=>onSelectProject(p.id)} style={{borderBottom:"1px solid #F8FAFC",cursor:"pointer"}}
                        onMouseEnter={e=>e.currentTarget.style.background="#F0F4FF"}
                        onMouseLeave={e=>e.currentTarget.style.background="transparent"}>
                        <td style={{padding:"10px 12px"}}><div style={{fontSize:13,fontWeight:600,color:"#1E293B"}}>{p.name}</div><div style={{fontSize:10,color:"#94A3B8",fontFamily:"monospace"}}>{p.id}</div></td>
                        <td style={{padding:"10px 12px",fontSize:12,color:"#64748B"}}>{p.client}</td>
                        <td style={{padding:"10px 12px"}}><Badge status={p.status}/></td>
                        <td style={{padding:"10px 12px",fontSize:13,fontWeight:700,color:"#334155",fontVariantNumeric:"tabular-nums"}}>{st.salesBase>0?fmt(st.salesBase,p.currency):<span style={{color:"#CBD5E1"}}>未入力</span>}</td>
                        <td style={{padding:"10px 12px",fontSize:13,fontWeight:700,color:st.grossProfit>=0?"#059669":"#DC2626",fontVariantNumeric:"tabular-nums"}}>{st.salesBase>0?fmt(st.grossProfit,p.currency):<span style={{color:"#CBD5E1"}}>—</span>}</td>
                        <td style={{padding:"10px 12px"}}>{st.salesBase>0?(<div style={{display:"flex",alignItems:"center",gap:8}}><div style={{flex:1,height:4,background:"#F1F5F9",borderRadius:2}}><div style={{height:"100%",width:`${Math.max(0,Math.min(100,st.grossMargin))}%`,background:st.grossMargin>=30?"#10B981":st.grossMargin>=15?"#F59E0B":"#EF4444",borderRadius:2}}/></div><span style={{fontSize:12,fontWeight:700,color:"#64748B",minWidth:36}}>{st.grossMargin.toFixed(0)}%</span></div>):<span style={{color:"#CBD5E1",fontSize:12}}>—</span>}</td>
                      </tr>
                    );
                  })
              }
            </tbody>
          </table>
        </div>
      </div>

    </div>
  );
};

// ─────────────────────────────────────────────
// MAIN APP
// ─────────────────────────────────────────────
export default function App() {
  const [currentUser,  setCurrentUser]  = useState(null);
  const [projects,     setProjects]     = useState(INIT_PROJECTS);
  const [users,        setUsers]        = useState(INIT_USERS);
  const [loginHistory, setLoginHistory] = useState(INIT_HISTORY);
  const [goals,        setGoals]        = useState(INIT_GOALS);
  const [view,         setView]         = useState("dashboard");
  const [selectedId,   setSelectedId]   = useState(null);
  const [modal,        setModal]        = useState(null);

  const selected   = projects.find(p=>p.id===selectedId);
  const addHistory = (h) => setLoginHistory(hs=>[h,...hs]);

  if (!currentUser) {
    return <LoginScreen users={users} onLogin={setCurrentUser} onAddHistory={addHistory}/>;
  }

  const handleAddProject    = (proj) => { setProjects(ps=>[...ps,proj]); setModal(null); setSelectedId(proj.id); };
  const handleEditProject   = (proj) => { setProjects(ps=>ps.map(p=>p.id===proj.id?proj:p)); setModal(null); };
  const handleDeleteProject = (pid)  => { setProjects(ps=>ps.filter(p=>p.id!==pid)); setSelectedId(null); };
  const handleAddSale       = (sale) => { setProjects(ps=>ps.map(p=>p.id===selectedId?{...p,sales:[...p.sales,sale]}:p)); setModal(null); };
  const handleAddPurchase   = (pur)  => { setProjects(ps=>ps.map(p=>p.id===selectedId?{...p,purchases:[...p.purchases,pur]}:p)); setModal(null); };
  const handleDeleteSale    = (pid,sid) => setProjects(ps=>ps.map(p=>p.id===pid?{...p,sales:p.sales.filter(s=>s.id!==sid)}:p));
  const handleDeletePurchase= (pid,rid) => setProjects(ps=>ps.map(p=>p.id===pid?{...p,purchases:p.purchases.filter(r=>r.id!==rid)}:p));
  const handleUpdateStatus  = (pid,status) => setProjects(ps=>ps.map(p=>p.id===pid?{...p,status}:p));
  const handleImport        = (newProjs) => setProjects(ps=>[...ps,...newProjs]);

  const navItems = [
    {id:"dashboard",label:"ダッシュボード",icon:"▣"},
    {id:"projects", label:"案件管理",      icon:"◉"},
    {id:"settings", label:"設定",          icon:"⚙",adminOnly:true},
  ];

  return (
    <div style={{display:"flex",height:"100vh",background:"#F8FAFC",overflow:"hidden",fontFamily:"-apple-system,BlinkMacSystemFont,'Hiragino Kaku Gothic Pro','Yu Gothic',sans-serif"}}>

      <aside style={{width:192,flexShrink:0,background:"#0F172A",display:"flex",flexDirection:"column"}}>
        <div style={{padding:"18px 16px 14px",borderBottom:"1px solid #1E293B"}}>
          <div style={{fontSize:13,fontWeight:800,color:"#F8FAFC",letterSpacing:-0.3}}>案件管理台帳</div>
          <div style={{fontSize:10,color:"#334155",marginTop:2}}>Project Ledger</div>
        </div>
        <nav style={{flex:1,padding:"12px 8px"}}>
          {navItems.filter(i=>!i.adminOnly||currentUser.role==="admin").map(item=>(
            <button key={item.id} onClick={()=>{setView(item.id);setSelectedId(null);}}
              style={{width:"100%",display:"flex",alignItems:"center",gap:10,padding:"9px 10px",borderRadius:8,border:"none",cursor:"pointer",textAlign:"left",background:view===item.id?"#4F46E5":"transparent",color:view===item.id?"#fff":"#64748B",fontSize:13,fontWeight:600,marginBottom:2}}>
              <span>{item.icon}</span>{item.label}
            </button>
          ))}
          <div style={{borderTop:"1px solid #1E293B",marginTop:16,paddingTop:12}}>
            <div style={{fontSize:10,color:"#475569",fontWeight:700,textTransform:"uppercase",letterSpacing:0.5,marginBottom:10,paddingLeft:10}}>入力フロー</div>
            {[{step:"①",label:"新規案件を登録",color:"#4F46E5",action:()=>setModal("newProject")},{step:"②",label:"売上明細を入力",color:"#059669",action:()=>selected&&setModal("sale")},{step:"③",label:"仕入明細を入力",color:"#DC2626",action:()=>selected&&setModal("purchase")}].map(f=>(
              <button key={f.step} onClick={f.action}
                style={{width:"100%",display:"flex",alignItems:"center",gap:8,padding:"7px 8px",borderRadius:7,border:"none",cursor:"pointer",textAlign:"left",background:"transparent",marginBottom:4}}
                onMouseEnter={e=>e.currentTarget.style.background="#1E293B"}
                onMouseLeave={e=>e.currentTarget.style.background="transparent"}>
                <span style={{width:20,height:20,borderRadius:"50%",background:f.color,display:"flex",alignItems:"center",justifyContent:"center",fontSize:10,color:"#fff",fontWeight:700,flexShrink:0}}>{f.step}</span>
                <span style={{fontSize:12,color:"#94A3B8"}}>{f.label}</span>
              </button>
            ))}
            {selected && (
              <div style={{marginTop:8,padding:"8px 10px",background:"#1E293B",borderRadius:8,fontSize:11,color:"#64748B"}}>
                選択中：<span style={{color:"#A5B4FC",fontWeight:600,display:"block",marginTop:2}}>{selected.name}</span>
              </div>
            )}
          </div>
        </nav>
        <div style={{padding:"12px 14px",borderTop:"1px solid #1E293B"}}>
          <div style={{display:"flex",alignItems:"center",gap:8,marginBottom:10}}>
            <div style={{width:28,height:28,borderRadius:"50%",background:"#4F46E5",display:"flex",alignItems:"center",justifyContent:"center",fontSize:11,fontWeight:700,color:"#fff",flexShrink:0}}>{currentUser.name.charAt(0)}</div>
            <div>
              <div style={{fontSize:12,fontWeight:600,color:"#E2E8F0"}}>{currentUser.name}</div>
              <div style={{fontSize:10,background:currentUser.role==="admin"?"#FEF3C7":"#E0F2FE",color:currentUser.role==="admin"?"#92400E":"#075985",borderRadius:4,padding:"1px 6px",display:"inline-block",fontWeight:700}}>{currentUser.role==="admin"?"管理者":"一般"}</div>
            </div>
          </div>
          <button onClick={()=>setCurrentUser(null)} style={{width:"100%",padding:"7px 0",fontSize:12,color:"#64748B",background:"#1E293B",border:"none",borderRadius:7,cursor:"pointer"}}>ログアウト</button>
        </div>
      </aside>

      <div style={{flex:1,display:"flex",flexDirection:"column",overflow:"hidden"}}>
        <header style={{background:"#fff",borderBottom:"1px solid #F1F5F9",padding:"11px 24px",display:"flex",alignItems:"center",justifyContent:"space-between",flexShrink:0}}>
          <div style={{fontSize:14,fontWeight:700,color:"#1E293B"}}>
            {view==="dashboard"?"ダッシュボード":view==="projects"?"案件管理":"設定"}
          </div>
          {view==="dashboard" && (
            <div style={{display:"flex",alignItems:"center",gap:8}}>
              <button onClick={()=>exportCSV(projects)} style={{padding:"7px 14px",fontSize:12,fontWeight:600,color:"#475569",border:"1px solid #E2E8F0",background:"#fff",borderRadius:8,cursor:"pointer"}}>📄 CSV出力</button>
              <button onClick={()=>setModal("import")} style={{padding:"7px 14px",fontSize:12,fontWeight:600,color:"#059669",border:"1px solid #A7F3D0",background:"#D1FAE5",borderRadius:8,cursor:"pointer"}}>📥 Excel取込</button>
              <button onClick={()=>setModal("newProject")} style={{padding:"7px 16px",fontSize:12,fontWeight:700,color:"#fff",background:"#4F46E5",border:"none",borderRadius:8,cursor:"pointer"}}>＋ 新規案件</button>
            </div>
          )}
          {view==="settings" && <div style={{fontSize:11,color:"#94A3B8"}}>管理者専用メニュー</div>}
        </header>
        <main style={{flex:1,overflowY:"auto",padding:24}}>
          {view==="dashboard" && <Dashboard projects={projects} goals={goals} onSelectProject={setSelectedId}/>}
          {view==="projects"  && <ProjectListView projects={projects} onSelectProject={setSelectedId} onNewProject={()=>setModal("newProject")} onExportCSV={()=>exportCSV(projects)} onImport={()=>setModal("import")}/>}
          {view==="settings"  && <SettingsView goals={goals} setGoals={setGoals} users={users} setUsers={setUsers} loginHistory={loginHistory} currentUser={currentUser}/>}
        </main>
      </div>

      {selectedId && selected && (
        <DetailPanel
          project={selected}
          onClose={()=>setSelectedId(null)}
          onAddSale={()=>setModal("sale")}
          onAddPurchase={()=>setModal("purchase")}
          onDeleteSale={handleDeleteSale}
          onDeletePurchase={handleDeletePurchase}
          onUpdateStatus={handleUpdateStatus}
          onEdit={()=>setModal("editProject")}
          onDelete={handleDeleteProject}
        />
      )}

      {modal==="newProject"  && <ProjectForm title="① 新規案件を登録する" initial={{name:"",client:"",clientDept:"",manager:"",status:"quote",currency:"JPY",category:"",probability:100,startDate:"",endDate:"",description:""}} onClose={()=>setModal(null)} onSave={(f)=>handleAddProject({...f,id:newPjId(projects),createdAt:today(),sales:[],purchases:[]})} projects={projects}/>}
      {modal==="editProject" && selected && <ProjectForm title="案件情報を編集" subtitle={selected.id} initial={selected} onClose={()=>setModal(null)} onSave={handleEditProject} projects={projects}/>}
      {modal==="sale"        && selected && <SaleModal project={selected} onClose={()=>setModal(null)} onAdd={handleAddSale}/>}
      {modal==="purchase"    && selected && <PurchaseModal project={selected} onClose={()=>setModal(null)} onAdd={handleAddPurchase}/>}
      {modal==="import"      && <ImportModal onClose={()=>setModal(null)} onImport={handleImport} projects={projects}/>}

    </div>
  );
}
