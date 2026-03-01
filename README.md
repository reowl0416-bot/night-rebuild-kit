<!doctype html>
<html lang="ja">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <meta name="color-scheme" content="dark light" />

  <title>Night Rebuild Kit | 予約導線が強い店舗サイトテンプレ</title>
  <meta name="description" content="スマホ最適化・固定CTA・料金/アクセス/求人まで。ナイト系店舗サイトを“見やすく・予約しやすく”する最小テンプレ。" />

  <!-- OGP (後で差し替えOK) -->
  <meta property="og:title" content="Night Rebuild Kit" />
  <meta property="og:description" content="見やすく、予約しやすく。ナイト系店舗サイトを刷新するテンプレ。" />
  <meta property="og:type" content="website" />

  <style>
    :root{
      --bg:#0b1020;
      --card:rgba(255,255,255,.06);
      --card2:rgba(255,255,255,.04);
      --hair:rgba(255,255,255,.10);
      --text:rgba(255,255,255,.92);
      --muted:rgba(255,255,255,.68);
      --accent:#7c3aed;   /* violet */
      --accent2:#22c55e;  /* green */
      --warn:#f59e0b;
      --shadow:0 18px 50px rgba(0,0,0,.45);
      --radius:18px;
      --max:1080px;
    }

    *{ box-sizing:border-box; }
    html,body{ height:100%; }
    body{
      margin:0;
      color:var(--text);
      font-family: ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Noto Sans JP", "Hiragino Kaku Gothic ProN", "Yu Gothic", "Meiryo", Arial, "Apple Color Emoji","Segoe UI Emoji";
      background:
        radial-gradient(900px 600px at 12% 10%, rgba(124,58,237,.22), transparent 60%),
        radial-gradient(800px 520px at 92% 18%, rgba(34,197,94,.12), transparent 55%),
        radial-gradient(1000px 700px at 40% 120%, rgba(56,189,248,.10), transparent 60%),
        var(--bg);
      overflow-x:hidden;
    }

    a{ color:inherit; text-decoration:none; }
    a:hover{ text-decoration:underline; text-underline-offset:4px; }

    .grid{
      position:fixed; inset:0;
      background:
        linear-gradient(to right, rgba(255,255,255,.05) 1px, transparent 1px),
        linear-gradient(to bottom, rgba(255,255,255,.05) 1px, transparent 1px);
      background-size: 56px 56px;
      mask-image: radial-gradient(60% 55% at 50% 18%, black 55%, transparent 100%);
      pointer-events:none;
      opacity:.25;
    }

    .wrap{
      width:min(var(--max), calc(100% - 48px));
      margin:0 auto;
      padding: 22px 0 64px;
      position:relative;
    }

    header{
      display:flex; align-items:center; justify-content:space-between;
      gap:16px;
      padding: 10px 0 14px;
    }

    .brand{ display:flex; gap:12px; align-items:center; }
    .logo{
      width:38px; height:38px; border-radius: 12px;
      background:
        radial-gradient(12px 12px at 30% 25%, rgba(255,255,255,.35), transparent 60%),
        linear-gradient(135deg, rgba(124,58,237,.95), rgba(34,197,94,.72));
      box-shadow: 0 10px 28px rgba(124,58,237,.20);
      border: 1px solid rgba(255,255,255,.14);
    }
    .brand .name{ display:flex; flex-direction:column; line-height:1.1; }
    .brand strong{ font-size:14px; font-weight:750; letter-spacing:.2px; }
    .brand span{ font-size:12px; color:var(--muted); }

    nav{
      display:flex; gap:10px; align-items:center;
      color: var(--muted);
      font-size: 13px;
      flex-wrap:wrap;
      justify-content:flex-end;
    }
    nav a{
      padding: 8px 10px;
      border-radius: 999px;
      border: 1px solid transparent;
    }
    nav a:hover{
      border-color: rgba(255,255,255,.14);
      background: rgba(255,255,255,.04);
      text-decoration:none;
    }

    .card{
      border-radius: var(--radius);
      background: linear-gradient(180deg, var(--card), var(--card2));
      border: 1px solid rgba(255,255,255,.10);
      box-shadow: var(--shadow);
      overflow:hidden;
    }

    .hero{
      margin-top: 14px;
      display:grid;
      grid-template-columns: 1.25fr .75fr;
      gap: 18px;
      align-items:stretch;
    }

    .hero-main{ padding: 24px 24px 22px; }
    .badge{
      display:inline-flex; gap:8px; align-items:center;
      padding: 8px 12px;
      border-radius: 999px;
      font-size: 12px;
      color: rgba(255,255,255,.80);
      border: 1px solid rgba(255,255,255,.14);
      background: rgba(255,255,255,.04);
      user-select:none;
    }
    .dot{
      width:8px; height:8px; border-radius:50%;
      background: var(--accent2);
      box-shadow: 0 0 0 4px rgba(34,197,94,.15);
    }

    h1{
      margin: 14px 0 10px;
      font-size: clamp(28px, 4vw, 44px);
      line-height: 1.08;
      letter-spacing: -0.02em;
    }
    .sub{
      margin: 0 0 18px;
      color: var(--muted);
      font-size: 14.5px;
      line-height: 1.65;
      max-width: 72ch;
    }

    .cta{
      display:flex; gap:12px; flex-wrap:wrap;
      margin-top: 16px;
      align-items:center;
    }

    .btn{
      display:inline-flex; align-items:center; gap:10px;
      padding: 11px 14px;
      border-radius: 12px;
      border: 1px solid rgba(255,255,255,.14);
      background: rgba(255,255,255,.04);
      font-size: 13.5px;
      color: rgba(255,255,255,.90);
      text-decoration:none;
      transition: transform .15s ease, background .15s ease, border-color .15s ease;
      will-change: transform;
    }
    .btn:hover{
      transform: translateY(-1px);
      background: rgba(255,255,255,.06);
      border-color: rgba(255,255,255,.22);
      text-decoration:none;
    }
    .btn.primary{
      border-color: rgba(124,58,237,.55);
      background: linear-gradient(135deg, rgba(124,58,237,.95), rgba(124,58,237,.45));
      box-shadow: 0 14px 30px rgba(124,58,237,.22);
    }
    .btn.primary:hover{
      border-color: rgba(124,58,237,.75);
      background: linear-gradient(135deg, rgba(124,58,237,1), rgba(124,58,237,.50));
    }
    .btn.green{
      border-color: rgba(34,197,94,.45);
      background: linear-gradient(135deg, rgba(34,197,94,.92), rgba(34,197,94,.35));
      box-shadow: 0 14px 30px rgba(34,197,94,.14);
    }

    .icon{ width:16px; height:16px; display:inline-block; }

    .hero-side{
      padding: 18px;
      display:flex;
      flex-direction:column;
      gap: 12px;
    }
    .pill{
      display:inline-flex; gap:8px; align-items:center;
      padding: 8px 10px;
      border-radius: 999px;
      font-size: 12px;
      border: 1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.04);
      color: rgba(255,255,255,.78);
      width: fit-content;
    }
    .pill b{ color: rgba(255,255,255,.90); }

    .meta{
      display:flex; flex-direction:column; gap: 10px;
      padding: 14px;
      border-radius: 14px;
      border: 1px solid rgba(255,255,255,.10);
      background: rgba(0,0,0,.18);
    }
    .meta .row{
      display:flex; justify-content:space-between; gap: 10px;
      font-size: 12.5px;
      color: var(--muted);
    }
    .meta .row strong{
      color: rgba(255,255,255,.84);
      font-weight: 650;
    }

    .sections{
      margin-top: 18px;
      display:grid;
      grid-template-columns: repeat(12, 1fr);
      gap: 16px;
    }

    section.block{
      grid-column: span 12;
      padding: 18px;
    }
    .block h2{
      margin: 0 0 10px;
      font-size: 14px;
      letter-spacing: .02em;
      text-transform: uppercase;
      color: rgba(255,255,255,.80);
    }
    .block p{
      margin: 0 0 12px;
      color: var(--muted);
      font-size: 13.5px;
      line-height: 1.65;
    }

    .cols{
      display:grid;
      grid-template-columns: repeat(12, 1fr);
      gap: 14px;
      margin-top: 12px;
    }
    .col6{ grid-column: span 6; }
    .col4{ grid-column: span 4; }

    .panel{
      border-radius: 14px;
      border: 1px solid rgba(255,255,255,.10);
      background: rgba(0,0,0,.16);
      padding: 14px;
    }
    .panel h3{
      margin: 0 0 8px;
      font-size: 13.5px;
      color: rgba(255,255,255,.86);
      letter-spacing: .01em;
    }

    .list{ margin:0; padding:0; list-style:none; display:flex; flex-direction:column; gap:10px; }
    .item{
      display:flex; gap:10px; align-items:flex-start;
      padding: 12px 12px;
      border-radius: 14px;
      border: 1px solid rgba(255,255,255,.10);
      background: rgba(0,0,0,.16);
    }
    .tick{
      width:18px; height:18px; border-radius: 6px;
      display:flex; align-items:center; justify-content:center;
      flex: 0 0 auto;
      margin-top: 1px;
      border: 1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.04);
      color: rgba(255,255,255,.85);
      font-size: 12px;
    }
    .tick.ok{
      border-color: rgba(34,197,94,.25);
      background: rgba(34,197,94,.12);
    }

    .price{
      display:flex; justify-content:space-between; align-items:flex-end;
      gap: 10px;
      padding: 12px 12px;
      border-radius: 14px;
      border: 1px solid rgba(255,255,255,.10);
      background: rgba(0,0,0,.16);
    }
    .price .name{ font-weight: 750; }
    .price .yen{ font-weight: 850; font-size: 18px; }
    .price small{ display:block; color: var(--muted); font-size: 12px; margin-top:4px; }

    .faq details{
      border-radius: 14px;
      border: 1px solid rgba(255,255,255,.10);
      background: rgba(0,0,0,.16);
      padding: 12px 12px;
    }
    .faq details + details{ margin-top: 10px; }
    .faq summary{
      cursor:pointer;
      font-weight: 700;
      color: rgba(255,255,255,.86);
      list-style:none;
    }
    .faq summary::-webkit-details-marker{ display:none; }
    .faq .a{
      margin-top: 8px;
      color: var(--muted);
      font-size: 13.5px;
      line-height: 1.65;
    }

    footer{
      margin-top: 22px;
      display:flex; justify-content:space-between; align-items:center;
      color: var(--muted);
      font-size: 12px;
      border-top: 1px solid rgba(255,255,255,.10);
      padding-top: 14px;
      gap: 12px;
      flex-wrap:wrap;
    }

    /* floating CTA (mobile friendly) */
    .fab{
      position: fixed;
      right: 18px;
      bottom: 18px;
      display:flex;
      gap: 10px;
      align-items:center;
      z-index: 999;
    }
    .fab a{
      display:inline-flex; align-items:center; gap:10px;
      padding: 12px 14px;
      border-radius: 999px;
      border: 1px solid rgba(255,255,255,.14);
      background: rgba(0,0,0,.30);
      backdrop-filter: blur(10px);
      -webkit-backdrop-filter: blur(10px);
      box-shadow: 0 16px 35px rgba(0,0,0,.35);
      text-decoration:none;
      color: rgba(255,255,255,.92);
      font-weight: 750;
      font-size: 13px;
    }
    .fab a.primary{
      border-color: rgba(124,58,237,.55);
      background: linear-gradient(135deg, rgba(124,58,237,.95), rgba(124,58,237,.35));
    }
    .fab a:hover{ transform: translateY(-1px); }

    /* fade-in */
    @media (prefers-reduced-motion: no-preference){
      .fade{ animation: fadeUp .55s ease both; }
      .d1{ animation-delay:.06s; }
      .d2{ animation-delay:.12s; }
      .d3{ animation-delay:.18s; }
      @keyframes fadeUp{
        from{ opacity:0; transform: translateY(8px); }
        to{ opacity:1; transform: translateY(0); }
      }
    }

    /* responsive */
    @media (max-width: 900px){
      .hero{ grid-template-columns: 1fr; }
      .wrap{ width:min(var(--max), calc(100% - 32px)); }
      nav{ display:none; }
      .col6, .col4{ grid-column: span 12; }
      .fab{ left: 16px; right: 16px; bottom: 14px; justify-content: center; }
      .fab a{ flex: 1; justify-content:center; }
    }
  </style>
</head>

<body>
  <div class="grid" aria-hidden="true"></div>

  <div class="wrap">
    <header class="fade">
      <div class="brand">
        <div class="logo" aria-hidden="true"></div>
        <div class="name">
          <strong>Night Rebuild Kit</strong>
          <span>店舗サイトを“見やすく・予約しやすく”</span>
        </div>
      </div>

      <nav aria-label="ページ内リンク">
        <a href="#features">強み</a>
        <a href="#pricing">料金</a>
        <a href="#access">アクセス</a>
        <a href="#faq">FAQ</a>
        <a href="#recruit">求人</a>
      </nav>
    </header>

    <main class="hero">
      <section class="card hero-main fade d1">
        <div class="badge">
          <span class="dot" aria-hidden="true"></span>
          <span>Mobile first • Fixed CTA • Fast</span>
        </div>

        <h1>「予約される」導線に、<br>サイトを塗り替える。</h1>

        <p class="sub">
          “古い・見づらい・予約まで遠い” を、最短で改善するためのテンプレ。
          料金/アクセス/FAQ/求人まで、必要な情報を一画面で迷わず届けます。
          <br>※このページは <code>index.html</code> 1枚で動きます（GitHub Pages向け）。
        </p>

        <div class="cta">
          <a class="btn primary" href="#contact">
            <svg class="icon" viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <path d="M12 5v14M5 12h14" stroke="currentColor" stroke-width="2" stroke-linecap="round" opacity=".9"/>
            </svg>
            予約・問い合わせ
          </a>

          <a class="btn green" href="https://line.me/R/ti/p/@YOUR_LINE_ID" target="_blank" rel="noreferrer">
            <svg class="icon" viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <path d="M20 12c0 4.4-4 8-8.9 8-.8 0-1.6-.1-2.3-.3L5 21l.9-3.2C4.7 16.5 4 14.8 4 13c0-4.4 4-8 8.9-8S20 7.6 20 12Z" stroke="currentColor" stroke-width="2" opacity=".9"/>
            </svg>
            LINEで連絡
          </a>

          <a class="btn" href="#pricing">
            <svg class="icon" viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <path d="M6 8h12M6 12h12M6 16h12" stroke="currentColor" stroke-width="2" stroke-linecap="round" opacity=".9"/>
            </svg>
            料金を見る
          </a>
        </div>
      </section>

      <aside class="card hero-side fade d2" aria-label="ステータス">
        <div class="pill"><b>Status</b>：デモ公開中</div>

        <div class="meta">
          <div class="row"><span>狙い</span><strong>予約率 / CVR</strong></div>
          <div class="row"><span>強み</span><strong>導線設計 + 見やすさ</strong></div>
          <div class="row"><span>最短納品</span><strong>1〜3日</strong></div>
          <div class="row"><span>運用</span><strong>月額保守OK</strong></div>
        </div>

        <div class="meta">
          <div class="row"><span>対応範囲</span><strong>FV / 料金 / 求人</strong></div>
          <div class="row"><span>スマホ</span><strong>最優先</strong></div>
          <div class="row"><span>表示速度</span><strong>軽量設計</strong></div>
        </div>
      </aside>
    </main>

    <!-- Features -->
    <section class="card block sections fade d2" id="features">
      <h2>Features</h2>
      <p>“ベテランっぽさ”は、派手さより「情報が迷子にならない設計」です。ここをテンプレ化しています。</p>

      <div class="cols">
        <div class="panel col4">
          <h3>固定CTA（最重要）</h3>
          <p>スクロールしても「予約/LINE」が常に見える。迷わせず、離脱を減らします。</p>
          <ul class="list">
            <li class="item"><div class="tick ok">✓</div><div>スマホでも押しやすい</div></li>
            <li class="item"><div class="tick ok">✓</div><div>電話/LINE/フォームに接続</div></li>
          </ul>
        </div>

        <div class="panel col4">
          <h3>料金表が読みやすい</h3>
          <p>料金は“見づらさ”が致命傷。最低限の表現で、誤解なく伝える設計にします。</p>
          <ul class="list">
            <li class="item"><div class="tick ok">✓</div><div>プラン・時間・注意書き</div></li>
            <li class="item"><div class="tick ok">✓</div><div>追い課金の説明も整理</div></li>
          </ul>
        </div>

        <div class="panel col4">
          <h3>アクセスが一瞬で分かる</h3>
          <p>駅出口/目印/所要時間。迷う要素を潰します（地図埋め込みも可）。</p>
          <ul class="list">
            <li class="item"><div class="tick ok">✓</div><div>住所・最寄り・目印</div></li>
            <li class="item"><div class="tick ok">✓</div><div>営業時間・定休日</div></li>
          </ul>
        </div>
      </div>
    </section>

    <!-- Pricing -->
    <section class="card block sections fade d3" id="pricing">
      <h2>Pricing</h2>
      <p>最初は“勝てる範囲”だけを確実に。要望が増えたら段階的に拡張します。</p>

      <div class="cols">
        <div class="panel col6">
          <h3>制作プラン（例）</h3>

          <div class="price">
            <div>
              <div class="name">ライト（1ページ）</div>
              <small>トップ刷新 / 導線整理 / スマホ最適化</small>
            </div>
            <div class="yen">¥30,000〜</div>
          </div>

          <div class="price" style="margin-top:10px;">
            <div>
              <div class="name">スタンダード（〜4ページ）</div>
              <small>トップ + 料金 + アクセス + 求人 / 画像最適化</small>
            </div>
            <div class="yen">¥50,000〜</div>
          </div>

          <div class="price" style="margin-top:10px;">
            <div>
              <div class="name">月額保守</div>
              <small>画像/文言差し替え（月◯回）/ 軽微修正</small>
            </div>
            <div class="yen">¥5,000〜</div>
          </div>
        </div>

        <div class="panel col6">
          <h3>納品までの流れ</h3>
          <ul class="list">
            <li class="item"><div class="tick ok">1</div><div><b>現状URL</b>共有 → 課題点を3つに絞る</div></li>
            <li class="item"><div class="tick ok">2</div><div><b>デモ作成</b>（このテンプレをベース）</div></li>
            <li class="item"><div class="tick ok">3</div><div><b>確認→修正</b> → 公開（Pages / サーバー）</div></li>
          </ul>
          <p style="margin-top:10px;">
            ※「いまのサイトをそのまま“見やすく”」が最短で成果が出ます。
          </p>
        </div>
      </div>
    </section>

    <!-- Access -->
    <section class="card block sections fade d3" id="access">
      <h2>Access</h2>
      <p>住所・最寄り・目印・営業時間を“1スクロール”で。</p>

      <div class="cols">
        <div class="panel col6">
          <h3>基本情報（例）</h3>
          <ul class="list">
            <li class="item"><div class="tick">📍</div><div>東京都〇〇区〇〇 1-2-3（例）</div></li>
            <li class="item"><div class="tick">🚃</div><div>最寄り：〇〇駅 / 徒歩5分（例）</div></li>
            <li class="item"><div class="tick">🕒</div><div>営業時間：18:00〜翌5:00（例）</div></li>
            <li class="item"><div class="tick">📅</div><div>定休日：不定休（例）</div></li>
          </ul>
        </div>

        <div class="panel col6">
          <h3>地図（任意）</h3>
          <p>ここにGoogleマップ埋め込みを入れられます。まずはテキストでOK。</p>
          <div class="item" style="align-items:center;">
            <div class="tick">🗺️</div>
            <div>
              <div><b>地図は後で追加</b></div>
              <div style="color:var(--muted); font-size:13px; line-height:1.55;">
                要望があれば埋め込み対応（サイトの見え方が一気に良くなる）
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ -->
    <section class="card block sections fade d3" id="faq">
      <h2>FAQ</h2>
      <p>“不安”が残ると予約されません。先回りで潰します。</p>

      <div class="faq">
        <details>
          <summary>Q. どのくらいで公開できますか？</summary>
          <div class="a">最短で1〜3日を目安にしています。まずは現状URLと、直したいポイント（3つ）を教えてください。</div>
        </details>
        <details>
          <summary>Q. 既存のサイトがあるけど、作り替えできますか？</summary>
          <div class="a">はい。全面リニューアルだけでなく「見やすさ・導線」だけの改善も可能です（最短で成果が出やすい）。</div>
        </details>
        <details>
          <summary>Q. 写真素材が少ない場合は？</summary>
          <div class="a">最初はテキスト設計と導線だけでも改善できます。必要なら“撮影/素材調整”の相談も可能です。</div>
        </details>
      </div>
    </section>

    <!-- Recruit -->
    <section class="card block sections fade d3" id="recruit">
      <h2>Recruit</h2>
      <p>求人ページは「条件が一瞬で分かる」ことが命。文章を圧縮して読みやすくします。</p>

      <div class="cols">
        <div class="panel col6">
          <h3>募集要項（例）</h3>
          <ul class="list">
            <li class="item"><div class="tick">💰</div><div>給与：日給〇〇〜 / 時給〇〇〜（例）</div></li>
            <li class="item"><div class="tick">⏱</div><div>勤務：週〇〜 / 時間帯 〇〇（例）</div></li>
            <li class="item"><div class="tick">📌</div><div>待遇：送迎 / 寮 / 日払い（例）</div></li>
          </ul>
        </div>

        <div class="panel col6">
          <h3>応募導線</h3>
          <p>応募は“迷わせない”。固定CTAからLINEに飛ばすのが強いです。</p>
          <ul class="list">
            <li class="item"><div class="tick ok">✓</div><div>LINE応募（推奨）</div></li>
            <li class="item"><div class="tick ok">✓</div><div>電話応募（任意）</div></li>
          </ul>
        </div>
      </div>
    </section>

    <!-- Contact -->
    <section class="card block sections fade d3" id="contact">
      <h2>Contact</h2>
      <p>ここだけ実案件では差し替えます（電話番号 / LINE / フォーム）。</p>

      <div class="cols">
        <div class="panel col6">
          <h3>予約（例）</h3>
          <ul class="list">
            <li class="item"><div class="tick ok">☎</div><div>電話：<a href="tel:00000000000">000-0000-0000</a></div></li>
            <li class="item"><div class="tick ok">💬</div><div>LINE：<a href="https://line.me/R/ti/p/@YOUR_LINE_ID" target="_blank" rel="noreferrer">@YOUR_LINE_ID</a></div></li>
          </ul>
        </div>

        <div class="panel col6">
          <h3>注意</h3>
          <p>このテンプレは“見やすさ/導線”に特化しています。決済や会員機能などは別途設計が必要です。</p>
          <div class="item">
            <div class="tick" style="border-color:rgba(245,158,11,.35); background:rgba(245,158,11,.12);">!</div>
            <div style="color:var(--muted); font-size:13.5px; line-height:1.65;">
              まずは「予約に必要な情報を整理」→「速度/導線」を固めるのが最短で成果が出ます。
            </div>
          </div>
        </div>
      </div>
    </section>

    <footer class="fade d3">
      <div>© <span id="y"></span> Night Rebuild Kit • Built for GitHub Pages</div>
      <div style="display:flex; gap:12px; align-items:center;">
        <a href="https://github.com/" target="_blank" rel="noreferrer">GitHub</a>
        <span>•</span>
        <a href="#contact">Contact</a>
      </div>
    </footer>
  </div>

  <!-- Floating CTA -->
  <div class="fab" aria-label="固定ボタン">
    <a class="primary" href="#contact">予約する</a>
    <a href="https://line.me/R/ti/p/@YOUR_LINE_ID" target="_blank" rel="noreferrer">LINE</a>
  </div>

  <script>
    document.getElementById("y").textContent = new Date().getFullYear();
  </script>
</body>
</html>
/* ===== スマホ最適化 ===== */
@media (max-width: 768px){

  .info-grid{
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .info-item{
    writing-mode: horizontal-tb;
    text-orientation: mixed;
    font-size: 18px;
    line-height: 1.8;
  }

  .info-item::before{
    display:none;
  }

}
