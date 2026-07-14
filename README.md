<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Portfolio of Ruel Christian Salvino, a Political Science graduate, legal researcher, and virtual operations professional.">
    <meta name="theme-color" content="#171513">
    <title>Ruel Christian Salvino | Portfolio</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600&family=Instrument+Serif:ital@0;1&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <style>
        :root {
            --ink: #171513;
            --ink-soft: #24201d;
            --cream: #f1e8dc;
            --paper: #f8f3eb;
            --clay: #be5a35;
            --clay-dark: #8e3f24;
            --sand: #c5b8a8;
            --line-dark: rgba(248, 243, 235, 0.16);
            --line-light: rgba(23, 21, 19, 0.18);
            --ease: cubic-bezier(0.16, 1, 0.3, 1);
        }

        * {
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
            scroll-padding-top: 80px;
        }

        body {
            margin: 0;
            background: var(--ink);
            color: var(--cream);
            font-family: "DM Sans", sans-serif;
            overflow-x: hidden;
        }

        body.menu-open,
        body.modal-open {
            overflow: hidden;
        }

        ::selection {
            color: var(--paper);
            background: var(--clay);
        }

        ::-webkit-scrollbar {
            width: 9px;
        }

        ::-webkit-scrollbar-track {
            background: var(--ink);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--clay);
            border: 2px solid var(--ink);
        }

        a,
        button,
        input,
        textarea {
            -webkit-tap-highlight-color: transparent;
        }

        a:focus-visible,
        button:focus-visible,
        input:focus-visible,
        textarea:focus-visible {
            outline: 2px solid var(--clay);
            outline-offset: 4px;
        }

        .serif {
            font-family: "Instrument Serif", serif;
        }

        .skip-link {
            position: fixed;
            left: 16px;
            top: -60px;
            z-index: 2000;
            background: var(--paper);
            color: var(--ink);
            padding: 12px 18px;
            transition: top 0.2s ease;
        }

        .skip-link:focus {
            top: 16px;
        }

        .site-nav {
            position: fixed;
            inset: 0 0 auto;
            z-index: 1000;
            height: 82px;
            padding: 0 clamp(20px, 5vw, 76px);
            display: flex;
            align-items: center;
            justify-content: space-between;
            border-bottom: 1px solid transparent;
            transition: height 0.45s var(--ease), background 0.45s ease, border-color 0.45s ease;
        }

        .site-nav.scrolled {
            height: 68px;
            background: rgba(23, 21, 19, 0.9);
            border-color: var(--line-dark);
            backdrop-filter: blur(18px);
        }

        .nav-brand {
            color: var(--paper);
            display: inline-flex;
            align-items: baseline;
            gap: 11px;
            text-decoration: none;
            letter-spacing: 0.08em;
            font-size: 13px;
            font-weight: 600;
            text-transform: uppercase;
        }

        .nav-brand-mark {
            color: var(--clay);
            font-family: "Instrument Serif", serif;
            font-size: 28px;
            font-style: italic;
            font-weight: 400;
            letter-spacing: -0.05em;
            line-height: 1;
        }

        .desktop-nav {
            display: flex;
            align-items: center;
            gap: 32px;
        }

        .desktop-nav a {
            color: rgba(248, 243, 235, 0.68);
            font-size: 12px;
            font-weight: 600;
            letter-spacing: 0.12em;
            position: relative;
            text-decoration: none;
            text-transform: uppercase;
            transition: color 0.25s ease;
        }

        .desktop-nav a::after {
            content: "";
            position: absolute;
            right: 0;
            bottom: -8px;
            left: 0;
            height: 1px;
            background: var(--clay);
            transform: scaleX(0);
            transform-origin: right;
            transition: transform 0.45s var(--ease);
        }

        .desktop-nav a:hover,
        .desktop-nav a.active {
            color: var(--paper);
        }

        .desktop-nav a:hover::after,
        .desktop-nav a.active::after {
            transform: scaleX(1);
            transform-origin: left;
        }

        .menu-button {
            display: none;
            width: 44px;
            height: 44px;
            align-items: center;
            justify-content: center;
            border: 0;
            color: var(--paper);
            background: transparent;
            cursor: pointer;
        }

        .menu-lines,
        .menu-lines::before,
        .menu-lines::after {
            width: 24px;
            height: 1px;
            background: currentColor;
            display: block;
            transition: transform 0.35s var(--ease), top 0.35s var(--ease);
        }

        .menu-lines {
            position: relative;
        }

        .menu-lines::before,
        .menu-lines::after {
            content: "";
            position: absolute;
            left: 0;
        }

        .menu-lines::before {
            top: -7px;
        }

        .menu-lines::after {
            top: 7px;
        }

        .menu-open .menu-lines {
            background: transparent;
        }

        .menu-open .menu-lines::before {
            top: 0;
            transform: rotate(45deg);
        }

        .menu-open .menu-lines::after {
            top: 0;
            transform: rotate(-45deg);
        }

        .mobile-menu {
            position: fixed;
            inset: 0;
            z-index: 900;
            display: grid;
            align-content: center;
            padding: 100px 24px 48px;
            background: var(--ink);
            visibility: hidden;
            opacity: 0;
            pointer-events: none;
            transform: translateY(-20px);
            transition: opacity 0.35s ease, transform 0.45s var(--ease), visibility 0.35s ease;
        }

        .menu-open .mobile-menu {
            visibility: visible;
            opacity: 1;
            pointer-events: auto;
            transform: translateY(0);
        }

        .mobile-menu a {
            color: var(--paper);
            border-bottom: 1px solid var(--line-dark);
            font-family: "Instrument Serif", serif;
            font-size: clamp(42px, 13vw, 68px);
            line-height: 1.18;
            text-decoration: none;
        }

        .hero {
            min-height: 100svh;
            position: relative;
            display: flex;
            align-items: flex-end;
            isolation: isolate;
            overflow: hidden;
            background: var(--ink);
        }

        .hero-media,
        .hero-media::after {
            position: absolute;
            inset: 0;
        }

        .hero-media {
            z-index: -2;
            overflow: hidden;
        }

        .hero-media img {
            width: 100%;
            height: 110%;
            object-fit: cover;
            object-position: 63% 28%;
            filter: saturate(0.72) contrast(1.08) brightness(0.78);
            animation: heroScale 14s var(--ease) both;
            will-change: transform;
        }

        .hero-media::after {
            content: "";
            background:
                linear-gradient(90deg, rgba(23, 21, 19, 0.97) 0%, rgba(23, 21, 19, 0.74) 43%, rgba(23, 21, 19, 0.16) 75%),
                linear-gradient(0deg, rgba(23, 21, 19, 0.9) 0%, transparent 55%);
        }

        @keyframes heroScale {
            from { transform: scale(1.08); }
            to { transform: scale(1); }
        }

        .hero-content {
            width: min(1500px, 100%);
            margin: 0 auto;
            padding: 150px clamp(20px, 5vw, 76px) clamp(48px, 8vh, 88px);
        }

        .hero-name {
            max-width: 1030px;
            margin: 0;
            color: var(--paper);
            font-family: "Instrument Serif", serif;
            font-size: clamp(74px, 10.9vw, 176px);
            font-weight: 400;
            letter-spacing: -0.055em;
            line-height: 0.72;
        }

        .hero-name span {
            display: block;
            opacity: 0;
            transform: translateY(55px);
            animation: heroIn 1.1s var(--ease) forwards;
        }

        .hero-name .first-name {
            animation-delay: 0.14s;
        }

        .hero-name .last-name {
            padding-left: 0.55em;
            color: var(--clay);
            font-style: italic;
            animation-delay: 0.28s;
        }

        @keyframes heroIn {
            to { opacity: 1; transform: translateY(0); }
        }

        .hero-intro {
            max-width: 640px;
            margin: 48px 0 0;
            display: grid;
            grid-template-columns: auto 1fr;
            gap: 22px;
            align-items: start;
            opacity: 0;
            transform: translateY(24px);
            animation: heroIn 0.9s 0.55s var(--ease) forwards;
        }

        .hero-intro::before {
            content: "";
            width: 72px;
            height: 1px;
            margin-top: 13px;
            background: var(--clay);
        }

        .hero-role {
            margin: 0 0 10px;
            color: var(--paper);
            font-size: clamp(15px, 1.5vw, 20px);
            font-weight: 600;
            letter-spacing: 0.02em;
        }

        .hero-copy {
            margin: 0;
            color: rgba(248, 243, 235, 0.67);
            font-size: 15px;
            line-height: 1.75;
        }

        .hero-actions {
            margin: 28px 0 0 94px;
            display: flex;
            align-items: center;
            gap: 26px;
            opacity: 0;
            transform: translateY(20px);
            animation: heroIn 0.9s 0.7s var(--ease) forwards;
        }

        .button-primary,
        .button-text {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 16px;
            min-height: 52px;
            color: inherit;
            font-size: 12px;
            font-weight: 600;
            letter-spacing: 0.12em;
            text-decoration: none;
            text-transform: uppercase;
            cursor: pointer;
        }

        .button-primary {
            padding: 0 24px;
            border: 1px solid var(--clay);
            color: var(--paper);
            background: var(--clay);
            transition: background 0.3s ease, color 0.3s ease, transform 0.3s var(--ease);
        }

        .button-primary:hover {
            background: var(--clay-dark);
            transform: translateY(-3px);
        }

        .button-primary svg,
        .button-text svg {
            width: 17px;
            transition: transform 0.35s var(--ease);
        }

        .button-primary:hover svg,
        .button-text:hover svg {
            transform: translateX(5px);
        }

        .button-text {
            min-height: auto;
            border: 0;
            border-bottom: 1px solid currentColor;
            color: var(--paper);
            background: none;
            padding: 0 0 7px;
        }

        .section-shell {
            width: min(1380px, 100%);
            margin: 0 auto;
            padding: clamp(92px, 12vw, 170px) clamp(20px, 5vw, 76px);
        }

        .section-kicker {
            display: flex;
            align-items: center;
            gap: 14px;
            margin: 0 0 24px;
            color: var(--clay);
            font-size: 11px;
            font-weight: 600;
            letter-spacing: 0.16em;
            text-transform: uppercase;
        }

        .section-kicker::before {
            content: "";
            width: 28px;
            height: 1px;
            background: currentColor;
        }

        .display-heading {
            max-width: 950px;
            margin: 0;
            font-family: "Instrument Serif", serif;
            font-size: clamp(54px, 8vw, 112px);
            font-weight: 400;
            letter-spacing: -0.045em;
            line-height: 0.93;
        }

        .about {
            color: var(--ink);
            background: var(--cream);
        }

        .about-heading em,
        .skills-heading em,
        .work-heading em,
        .contact-heading em {
            color: var(--clay);
            font-weight: 400;
        }

        .about-layout {
            display: grid;
            grid-template-columns: minmax(280px, 0.82fr) minmax(340px, 1.18fr);
            gap: clamp(50px, 8vw, 120px);
            align-items: start;
            margin-top: clamp(60px, 9vw, 120px);
        }

        .about-image-wrap {
            position: relative;
            overflow: hidden;
            aspect-ratio: 4 / 5;
            background: #b9aa98;
        }

        .about-image-wrap img {
            width: 100%;
            height: 112%;
            object-fit: cover;
            object-position: center;
            filter: sepia(0.18) saturate(0.8);
            transition: filter 0.8s ease, transform 1.2s var(--ease);
        }

        .about-image-wrap:hover img {
            filter: sepia(0) saturate(1);
            transform: scale(1.035);
        }

        .image-note {
            margin: 12px 0 0;
            color: rgba(23, 21, 19, 0.5);
            font-size: 10px;
            letter-spacing: 0.12em;
            text-transform: uppercase;
        }

        .about-lead {
            margin: 0;
            font-family: "Instrument Serif", serif;
            font-size: clamp(30px, 3.3vw, 48px);
            letter-spacing: -0.02em;
            line-height: 1.12;
        }

        .about-copy {
            max-width: 660px;
            margin: 28px 0 0;
            color: rgba(23, 21, 19, 0.66);
            font-size: 16px;
            line-height: 1.85;
        }

        .timeline {
            margin: 54px 0 0;
            border-top: 1px solid var(--line-light);
        }

        .timeline-item {
            display: grid;
            grid-template-columns: 115px 1fr;
            gap: 20px;
            padding: 26px 0;
            border-bottom: 1px solid var(--line-light);
        }

        .timeline-year {
            color: var(--clay);
            font-size: 12px;
            font-weight: 600;
            letter-spacing: 0.1em;
        }

        .timeline-item h3 {
            margin: 0 0 7px;
            font-family: "Instrument Serif", serif;
            font-size: 24px;
            font-weight: 400;
        }

        .timeline-item p {
            margin: 0;
            color: rgba(23, 21, 19, 0.57);
            font-size: 14px;
            line-height: 1.65;
        }

        .skills {
            background: var(--ink-soft);
        }

        .skills-heading {
            max-width: 820px;
        }

        .skills-intro {
            max-width: 560px;
            margin: 28px 0 0 auto;
            color: rgba(248, 243, 235, 0.56);
            line-height: 1.8;
        }

        .skills-list {
            margin-top: clamp(62px, 9vw, 110px);
            border-top: 1px solid var(--line-dark);
        }

        .skill-row {
            display: grid;
            grid-template-columns: 80px minmax(220px, 0.8fr) 1.2fr;
            gap: 24px;
            align-items: center;
            min-height: 118px;
            border-bottom: 1px solid var(--line-dark);
            transition: padding 0.45s var(--ease), color 0.3s ease;
        }

        .skill-row:hover {
            padding-left: 18px;
        }

        .skill-index {
            color: var(--clay);
            font-family: "Instrument Serif", serif;
            font-size: 22px;
            font-style: italic;
        }

        .skill-row h3 {
            margin: 0;
            font-family: "Instrument Serif", serif;
            font-size: clamp(26px, 3vw, 42px);
            font-weight: 400;
        }

        .skill-row p {
            margin: 0;
            color: rgba(248, 243, 235, 0.5);
            font-size: 14px;
            line-height: 1.7;
        }

        .work {
            color: var(--ink);
            background: var(--paper);
        }

        .work-header {
            display: flex;
            justify-content: space-between;
            align-items: end;
            gap: 40px;
        }

        .filters {
            display: flex;
            flex-wrap: wrap;
            justify-content: flex-end;
            gap: 8px;
        }

        .filter-button {
            min-height: 42px;
            padding: 0 17px;
            border: 1px solid var(--line-light);
            border-radius: 999px;
            color: rgba(23, 21, 19, 0.62);
            background: transparent;
            font-family: inherit;
            font-size: 11px;
            font-weight: 600;
            letter-spacing: 0.08em;
            text-transform: uppercase;
            cursor: pointer;
            transition: color 0.25s ease, background 0.25s ease, border-color 0.25s ease;
        }

        .filter-button:hover,
        .filter-button.active {
            color: var(--paper);
            border-color: var(--ink);
            background: var(--ink);
        }

        .project-grid {
            display: grid;
            grid-template-columns: repeat(12, 1fr);
            gap: clamp(22px, 3vw, 42px);
            margin-top: clamp(58px, 8vw, 100px);
        }

        .project {
            grid-column: span 4;
            min-width: 0;
            opacity: 1;
            transform: translateY(0) scale(1);
            transition: opacity 0.35s ease, transform 0.5s var(--ease);
        }

        .project.is-hiding {
            opacity: 0;
            transform: translateY(18px) scale(0.98);
            pointer-events: none;
        }

        .project[hidden] {
            display: none;
        }

        .project:nth-child(2) {
            margin-top: 90px;
        }

        .project-media {
            width: 100%;
            padding: 0;
            border: 0;
            aspect-ratio: 4 / 5;
            position: relative;
            overflow: hidden;
            background: #c7b8a7;
            cursor: pointer;
        }

        .project-media::after {
            content: "View project";
            position: absolute;
            right: 18px;
            bottom: 18px;
            padding: 10px 14px;
            color: var(--paper);
            background: var(--ink);
            font-family: "DM Sans", sans-serif;
            font-size: 10px;
            font-weight: 600;
            letter-spacing: 0.1em;
            text-transform: uppercase;
            opacity: 0;
            transform: translateY(12px);
            transition: opacity 0.35s ease, transform 0.35s var(--ease);
        }

        .project-media:hover::after,
        .project-media:focus-visible::after {
            opacity: 1;
            transform: translateY(0);
        }

        .project-media img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            filter: saturate(0.75);
            transition: transform 0.9s var(--ease), filter 0.5s ease;
        }

        .project-media:hover img,
        .project-media:focus-visible img {
            transform: scale(1.06);
            filter: saturate(1);
        }

        .project-meta {
            display: flex;
            justify-content: space-between;
            gap: 20px;
            margin-top: 20px;
            color: var(--clay);
            font-size: 10px;
            font-weight: 600;
            letter-spacing: 0.12em;
            text-transform: uppercase;
        }

        .project h3 {
            margin: 10px 0 0;
            font-family: "Instrument Serif", serif;
            font-size: clamp(29px, 3.1vw, 44px);
            font-weight: 400;
            letter-spacing: -0.025em;
            line-height: 1.04;
        }

        .project p {
            margin: 13px 0 0;
            color: rgba(23, 21, 19, 0.58);
            font-size: 14px;
            line-height: 1.7;
        }

        .credentials {
            position: relative;
            isolation: isolate;
            background: var(--clay-dark);
            overflow: hidden;
        }

        .credentials::before {
            content: "RCS";
            position: absolute;
            right: -0.06em;
            bottom: -0.25em;
            z-index: -1;
            color: rgba(248, 243, 235, 0.045);
            font-family: "Instrument Serif", serif;
            font-size: min(43vw, 620px);
            font-style: italic;
            line-height: 1;
            animation: monogramFloat 11s ease-in-out infinite alternate;
        }

        @keyframes monogramFloat {
            to { transform: translate3d(-24px, -16px, 0); }
        }

        .credentials .section-kicker {
            color: var(--paper);
        }

        .credential-layout {
            display: grid;
            grid-template-columns: 0.86fr 1.14fr;
            gap: clamp(50px, 9vw, 130px);
            align-items: start;
        }

        .credential-copy {
            position: sticky;
            top: 110px;
        }

        .credential-copy .display-heading {
            font-size: clamp(54px, 7vw, 96px);
        }

        .credential-copy p {
            max-width: 470px;
            margin: 28px 0 0;
            color: rgba(248, 243, 235, 0.7);
            line-height: 1.8;
        }

        .credential-list {
            border-top: 1px solid rgba(248, 243, 235, 0.34);
        }

        .credential-item {
            display: grid;
            grid-template-columns: 80px 1fr;
            gap: 18px;
            padding: 34px 0;
            border-bottom: 1px solid rgba(248, 243, 235, 0.34);
        }

        .credential-item > span {
            font-family: "Instrument Serif", serif;
            font-size: 36px;
            font-style: italic;
        }

        .credential-item h3 {
            margin: 0 0 9px;
            font-family: "Instrument Serif", serif;
            font-size: clamp(25px, 3vw, 38px);
            font-weight: 400;
            line-height: 1.06;
        }

        .credential-item p {
            margin: 0;
            color: rgba(248, 243, 235, 0.68);
            font-size: 13px;
            line-height: 1.7;
        }

        .contact {
            color: var(--ink);
            background: var(--cream);
        }

        .contact-layout {
            display: grid;
            grid-template-columns: 0.92fr 1.08fr;
            gap: clamp(50px, 9vw, 130px);
            align-items: start;
        }

        .contact-copy > p {
            max-width: 520px;
            margin: 30px 0 0;
            color: rgba(23, 21, 19, 0.63);
            font-size: 16px;
            line-height: 1.8;
        }

        .contact-links {
            display: grid;
            gap: 12px;
            margin-top: 48px;
        }

        .contact-link {
            width: fit-content;
            color: var(--ink);
            border-bottom: 1px solid rgba(23, 21, 19, 0.35);
            font-family: "Instrument Serif", serif;
            font-size: clamp(23px, 2.8vw, 35px);
            text-decoration: none;
            transition: color 0.25s ease, border-color 0.25s ease;
        }

        .contact-link:hover {
            color: var(--clay);
            border-color: var(--clay);
        }

        .contact-location {
            margin-top: 16px;
            color: rgba(23, 21, 19, 0.52);
            font-size: 12px;
            letter-spacing: 0.1em;
            text-transform: uppercase;
        }

        .contact-form {
            padding: clamp(28px, 4.5vw, 58px);
            color: var(--paper);
            background: var(--ink);
        }

        .form-heading {
            margin: 0 0 34px;
            font-family: "Instrument Serif", serif;
            font-size: 34px;
            font-weight: 400;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .form-field {
            position: relative;
            margin-bottom: 24px;
        }

        .form-field label {
            display: block;
            margin-bottom: 9px;
            color: rgba(248, 243, 235, 0.6);
            font-size: 10px;
            font-weight: 600;
            letter-spacing: 0.13em;
            text-transform: uppercase;
        }

        .form-field input,
        .form-field textarea {
            width: 100%;
            border: 0;
            border-bottom: 1px solid rgba(248, 243, 235, 0.25);
            border-radius: 0;
            padding: 10px 0 13px;
            color: var(--paper);
            background: transparent;
            font: inherit;
            transition: border-color 0.25s ease;
        }

        .form-field input::placeholder,
        .form-field textarea::placeholder {
            color: rgba(248, 243, 235, 0.28);
        }

        .form-field input:focus,
        .form-field textarea:focus {
            border-color: var(--clay);
            outline: 0;
        }

        .form-field textarea {
            min-height: 112px;
            resize: vertical;
        }

        .form-footer {
            display: flex;
            align-items: center;
            gap: 18px;
            margin-top: 8px;
        }

        .form-status {
            margin: 0;
            color: rgba(248, 243, 235, 0.62);
            font-size: 12px;
            line-height: 1.5;
        }

        .site-footer {
            padding: 30px clamp(20px, 5vw, 76px);
            background: var(--ink);
            border-top: 1px solid var(--line-dark);
        }

        .footer-inner {
            width: min(1230px, 100%);
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 20px;
            color: rgba(248, 243, 235, 0.43);
            font-size: 11px;
            letter-spacing: 0.08em;
            text-transform: uppercase;
        }

        .footer-inner a {
            color: inherit;
            text-decoration: none;
            transition: color 0.25s ease;
        }

        .footer-inner a:hover {
            color: var(--paper);
        }

        .project-modal {
            position: fixed;
            inset: 0;
            z-index: 1500;
            display: grid;
            place-items: center;
            padding: 20px;
            visibility: hidden;
            opacity: 0;
            background: rgba(23, 21, 19, 0.84);
            backdrop-filter: blur(14px);
            transition: opacity 0.35s ease, visibility 0.35s ease;
        }

        .project-modal.open {
            visibility: visible;
            opacity: 1;
        }

        .modal-panel {
            width: min(1050px, 100%);
            max-height: min(740px, calc(100svh - 40px));
            display: grid;
            grid-template-columns: 1.05fr 0.95fr;
            overflow: auto;
            color: var(--ink);
            background: var(--paper);
            transform: translateY(28px) scale(0.98);
            transition: transform 0.5s var(--ease);
        }

        .project-modal.open .modal-panel {
            transform: translateY(0) scale(1);
        }

        .modal-image {
            min-height: 560px;
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .modal-content {
            position: relative;
            display: flex;
            flex-direction: column;
            justify-content: center;
            padding: clamp(34px, 6vw, 72px);
        }

        .modal-close {
            position: absolute;
            top: 20px;
            right: 20px;
            width: 42px;
            height: 42px;
            display: grid;
            place-items: center;
            border: 1px solid var(--line-light);
            border-radius: 50%;
            color: var(--ink);
            background: transparent;
            font-size: 24px;
            line-height: 1;
            cursor: pointer;
            transition: color 0.25s ease, background 0.25s ease, transform 0.35s var(--ease);
        }

        .modal-close:hover {
            color: var(--paper);
            background: var(--ink);
            transform: rotate(90deg);
        }

        .modal-category {
            color: var(--clay);
            font-size: 10px;
            font-weight: 600;
            letter-spacing: 0.14em;
            text-transform: uppercase;
        }

        .modal-title {
            margin: 16px 0 22px;
            font-family: "Instrument Serif", serif;
            font-size: clamp(42px, 5vw, 66px);
            font-weight: 400;
            letter-spacing: -0.04em;
            line-height: 0.96;
        }

        .modal-description {
            margin: 0 0 28px;
            color: rgba(23, 21, 19, 0.62);
            font-size: 15px;
            line-height: 1.78;
        }

        .modal-detail {
            padding: 17px 0;
            border-top: 1px solid var(--line-light);
            color: rgba(23, 21, 19, 0.65);
            font-size: 13px;
        }

        .modal-detail strong {
            display: inline-block;
            min-width: 90px;
            color: var(--ink);
        }

        .modal-content .button-primary {
            width: fit-content;
            margin-top: 28px;
        }

        .reveal {
            opacity: 0;
            transform: translateY(38px);
            transition: opacity 0.8s ease, transform 0.9s var(--ease);
        }

        .reveal.is-visible {
            opacity: 1;
            transform: translateY(0);
        }

        .reveal-delay-1 { transition-delay: 0.12s; }
        .reveal-delay-2 { transition-delay: 0.24s; }
        .reveal-delay-3 { transition-delay: 0.36s; }

        @media (max-width: 960px) {
            .desktop-nav {
                display: none;
            }

            .menu-button {
                display: flex;
            }

            .hero-name {
                font-size: clamp(70px, 15vw, 135px);
                line-height: 0.78;
            }

            .about-layout,
            .credential-layout,
            .contact-layout {
                grid-template-columns: 1fr;
            }

            .about-image-wrap {
                max-width: 640px;
                aspect-ratio: 5 / 4;
            }

            .credential-copy {
                position: static;
            }

            .project {
                grid-column: span 6;
            }

            .project:nth-child(2) {
                margin-top: 70px;
            }

            .project:nth-child(3) {
                margin-top: 0;
            }

            .work-header {
                display: block;
            }

            .filters {
                justify-content: flex-start;
                margin-top: 34px;
            }
        }

        @media (max-width: 700px) {
            .site-nav {
                height: 68px;
            }

            .nav-brand {
                font-size: 11px;
            }

            .hero-media img {
                object-position: 61% 26%;
            }

            .hero-media::after {
                background:
                    linear-gradient(90deg, rgba(23, 21, 19, 0.72), rgba(23, 21, 19, 0.2)),
                    linear-gradient(0deg, rgba(23, 21, 19, 0.98) 0%, rgba(23, 21, 19, 0.67) 54%, transparent 100%);
            }

            .hero-content {
                padding-bottom: 42px;
            }

            .hero-name {
                font-size: clamp(54px, 17vw, 90px);
                line-height: 0.8;
            }

            .hero-name .last-name {
                padding-left: 0.12em;
            }

            .hero-intro {
                grid-template-columns: 38px 1fr;
                gap: 14px;
                margin-top: 36px;
            }

            .hero-intro::before {
                width: 38px;
            }

            .hero-copy {
                font-size: 13px;
                line-height: 1.65;
            }

            .hero-actions {
                margin-left: 52px;
                gap: 18px;
            }

            .button-primary {
                min-height: 48px;
                padding: 0 18px;
            }

            .display-heading {
                font-size: clamp(52px, 16vw, 76px);
            }

            .timeline-item {
                grid-template-columns: 1fr;
                gap: 8px;
            }

            .skill-row {
                grid-template-columns: 42px 1fr;
                gap: 12px;
                padding: 26px 0;
            }

            .skill-row p {
                grid-column: 2;
            }

            .skill-row:hover {
                padding-left: 8px;
            }

            .project-grid {
                grid-template-columns: 1fr;
            }

            .project,
            .project:nth-child(2),
            .project:nth-child(3) {
                grid-column: 1;
                margin-top: 0;
            }

            .project-media {
                aspect-ratio: 5 / 4;
            }

            .credential-item {
                grid-template-columns: 50px 1fr;
            }

            .form-row {
                grid-template-columns: 1fr;
                gap: 0;
            }

            .form-footer {
                align-items: flex-start;
                flex-direction: column;
            }

            .modal-panel {
                grid-template-columns: 1fr;
                max-height: calc(100svh - 24px);
            }

            .modal-image {
                min-height: 0;
                height: 230px;
            }

            .modal-content {
                padding: 38px 28px;
            }

            .modal-close {
                top: 14px;
                right: 14px;
                color: var(--paper);
                border-color: rgba(248, 243, 235, 0.45);
                background: rgba(23, 21, 19, 0.55);
                transform: translateY(-230px);
            }

            .modal-close:hover {
                transform: translateY(-230px) rotate(90deg);
            }

            .footer-inner {
                align-items: flex-start;
                flex-direction: column;
            }
        }

        @media (max-width: 450px) {
            .hero-actions {
                align-items: flex-start;
                flex-direction: column;
            }

            .button-text {
                margin-left: 2px;
            }

            .filters {
                gap: 6px;
            }

            .filter-button {
                min-height: 38px;
                padding: 0 13px;
                font-size: 9px;
            }
        }

        @media (prefers-reduced-motion: reduce) {
            html {
                scroll-behavior: auto;
            }

            *,
            *::before,
            *::after {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                scroll-behavior: auto !important;
                transition-duration: 0.01ms !important;
            }

            .reveal {
                opacity: 1;
                transform: none;
            }
        }
    </style>
</head>
<body>
    <a class="skip-link" href="#main">Skip to content</a>

    <header>
        <nav class="site-nav" id="siteNav" aria-label="Primary navigation">
            <a class="nav-brand" href="#home" aria-label="Ruel Christian Salvino, home">
                <span class="nav-brand-mark">R.</span>
                <span>Ruel Salvino</span>
            </a>
            <div class="desktop-nav">
                <a href="#about">About</a>
                <a href="#skills">Capabilities</a>
                <a href="#work">Work</a>
                <a href="#credentials">Credentials</a>
                <a href="#contact">Contact</a>
            </div>
            <button class="menu-button" id="menuButton" type="button" aria-label="Open navigation menu" aria-expanded="false" aria-controls="mobileMenu">
                <span class="menu-lines" aria-hidden="true"></span>
            </button>
        </nav>

        <div class="mobile-menu" id="mobileMenu" aria-hidden="true" inert>
            <a href="#about">About</a>
            <a href="#skills">Capabilities</a>
            <a href="#work">Selected work</a>
            <a href="#credentials">Credentials</a>
            <a href="#contact">Contact</a>
        </div>
    </header>

    <main id="main">
        <section class="hero" id="home" aria-labelledby="hero-title">
            <div class="hero-media" aria-hidden="true">
                <!-- Replace this editorial placeholder with Ruel's own portrait. -->
                <img id="heroImage" src="https://images.pexels.com/photos/24425379/pexels-photo-24425379.jpeg?auto=compress&cs=tinysrgb&fit=crop&h=1400&w=1800" alt="">
            </div>
            <div class="hero-content">
                <h1 class="hero-name" id="hero-title">
                    <span class="first-name">Ruel Christian</span>
                    <span class="last-name">Salvino</span>
                </h1>
                <div class="hero-intro">
                    <div>
                        <p class="hero-role">Political Science Graduate &amp; Legal Operations Professional</p>
                        <p class="hero-copy">Bringing academic precision, clear communication, and dependable execution to legal research, administrative support, and digital production.</p>
                    </div>
                </div>
                <div class="hero-actions">
                    <a class="button-primary" href="#contact">
                        Work with me
                        <svg viewBox="0 0 20 20" fill="none" aria-hidden="true"><path d="M3 10h14M12 5l5 5-5 5" stroke="currentColor" stroke-width="1.5"/></svg>
                    </a>
                    <a class="button-text" href="#work">Explore work</a>
                </div>
            </div>
        </section>

        <section class="about" id="about" aria-labelledby="about-title">
            <div class="section-shell">
                <p class="section-kicker reveal">01 / Biography</p>
                <h2 class="display-heading about-heading reveal reveal-delay-1" id="about-title">Built on curiosity.<br><em>Grounded in service.</em></h2>

                <div class="about-layout">
                    <div class="reveal">
                        <div class="about-image-wrap">
                            <!-- Replace this graduation placeholder with Ruel's own photo. -->
                            <img class="parallax-image" src="https://images.pexels.com/photos/17615714/pexels-photo-17615714.jpeg?auto=compress&cs=tinysrgb&fit=crop&h=1100&w=900" alt="Graduates celebrating at a university ceremony">
                        </div>
                    </div>

                    <div>
                        <p class="about-lead reveal">I turn complex information into clear, useful work, whether that means reviewing a legal record, shaping a research brief, or organizing a remote workflow.</p>
                        <p class="about-copy reveal reveal-delay-1">I graduated Magna Cum Laude in 2025 with a Bachelor of Arts in Political Science from the University of Nueva Caceres. Across academic, legal, and virtual roles, I developed a calm, systematic approach to detail-heavy work and a genuine commitment to continuous learning.</p>

                        <div class="timeline" aria-label="Education and experience timeline">
                            <article class="timeline-item reveal">
                                <span class="timeline-year">2021 - 2025</span>
                                <div>
                                    <h3>Bachelor of Arts in Political Science</h3>
                                    <p>University of Nueva Caceres. Graduated Magna Cum Laude with consistent academic distinction.</p>
                                </div>
                            </article>
                            <article class="timeline-item reveal reveal-delay-1">
                                <span class="timeline-year">October 2024</span>
                                <div>
                                    <h3>Provincial Prosecutor's Office</h3>
                                    <p>Completed a 200-hour internship supporting legal record review, pleadings, and administrative preparation.</p>
                                </div>
                            </article>
                            <article class="timeline-item reveal reveal-delay-2">
                                <span class="timeline-year">Now</span>
                                <div>
                                    <h3>Ready for the next brief</h3>
                                    <p>Seeking legal assistance, research, virtual operations, and thoughtful digital production opportunities.</p>
                                </div>
                            </article>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="skills" id="skills" aria-labelledby="skills-title">
            <div class="section-shell">
                <p class="section-kicker reveal">02 / Capabilities</p>
                <h2 class="display-heading skills-heading reveal reveal-delay-1" id="skills-title">Precision where it matters.<br><em>Adaptability everywhere else.</em></h2>
                <p class="skills-intro reveal reveal-delay-2">A multidisciplinary toolkit shaped by legal training, editorial judgment, remote collaboration, and a willingness to learn new systems quickly.</p>

                <div class="skills-list">
                    <article class="skill-row reveal">
                        <span class="skill-index">01</span>
                        <h3>Legal research</h3>
                        <p>Case synthesis, constitutional references, issue spotting, source verification, and concise legal writing.</p>
                    </article>
                    <article class="skill-row reveal">
                        <span class="skill-index">02</span>
                        <h3>Document systems</h3>
                        <p>Structured file management, pleadings assembly, manuscript formatting, records review, and quality control.</p>
                    </article>
                    <article class="skill-row reveal">
                        <span class="skill-index">03</span>
                        <h3>Virtual operations</h3>
                        <p>Calendar and task coordination, responsive communication, independent execution, and reliable follow-through.</p>
                    </article>
                    <article class="skill-row reveal">
                        <span class="skill-index">04</span>
                        <h3>Creative production</h3>
                        <p>Canva layouts, editorial graphics, video pacing, dynamic subtitles, and social-first content preparation.</p>
                    </article>
                    <article class="skill-row reveal">
                        <span class="skill-index">05</span>
                        <h3>AI-assisted work</h3>
                        <p>Responsible prompt design and workflow support across ChatGPT, Claude, and Gemini, with human review at every stage.</p>
                    </article>
                </div>
            </div>
        </section>

        <section class="work" id="work" aria-labelledby="work-title">
            <div class="section-shell">
                <div class="work-header">
                    <div>
                        <p class="section-kicker reveal">03 / Selected work</p>
                        <h2 class="display-heading work-heading reveal reveal-delay-1" id="work-title">Work with <em>purpose.</em></h2>
                    </div>
                    <div class="filters reveal" role="group" aria-label="Filter projects">
                        <button class="filter-button active" type="button" data-filter="all" aria-pressed="true">All</button>
                        <button class="filter-button" type="button" data-filter="legal" aria-pressed="false">Legal</button>
                        <button class="filter-button" type="button" data-filter="design" aria-pressed="false">Design</button>
                        <button class="filter-button" type="button" data-filter="video" aria-pressed="false">Video</button>
                    </div>
                </div>

                <div class="project-grid" id="projectGrid" aria-live="polite">
                    <article class="project reveal" data-category="legal">
                        <button class="project-media" type="button" data-project="legal" aria-label="View details for Pleadings and Formal Briefs">
                            <img src="https://images.pexels.com/photos/7876093/pexels-photo-7876093.jpeg?auto=compress&cs=tinysrgb&fit=crop&h=1000&w=800" alt="Legal workspace with documents, laptop, and Lady Justice statue">
                        </button>
                        <div class="project-meta"><span>Legal writing</span><span>01</span></div>
                        <h3>Pleadings &amp; Formal Briefs</h3>
                        <p>Clear, citation-led documents created for academic and practice-based legal exercises.</p>
                    </article>

                    <article class="project reveal reveal-delay-1" data-category="design">
                        <button class="project-media" type="button" data-project="design" aria-label="View details for Editorial Layout Systems">
                            <img src="https://images.pexels.com/photos/6143824/pexels-photo-6143824.jpeg?auto=compress&cs=tinysrgb&fit=crop&h=1000&w=800" alt="Hands reviewing an editorial design magazine on a desk">
                        </button>
                        <div class="project-meta"><span>Graphic design</span><span>02</span></div>
                        <h3>Editorial Layout Systems</h3>
                        <p>Structured manuscripts, presentation decks, and repeatable visual templates for digital publishing.</p>
                    </article>

                    <article class="project reveal reveal-delay-2" data-category="video">
                        <button class="project-media" type="button" data-project="video" aria-label="View details for Social Video Campaigns">
                            <img src="https://images.pexels.com/photos/29505140/pexels-photo-29505140.jpeg?auto=compress&cs=tinysrgb&fit=crop&h=1000&w=800" alt="Close view of a professional video editing timeline">
                        </button>
                        <div class="project-meta"><span>Video editing</span><span>03</span></div>
                        <h3>Social Video Campaigns</h3>
                        <p>Focused edits with strong pacing, readable subtitles, and platform-ready delivery.</p>
                    </article>
                </div>
            </div>
        </section>

        <section class="credentials" id="credentials" aria-labelledby="credentials-title">
            <div class="section-shell credential-layout">
                <div class="credential-copy">
                    <p class="section-kicker reveal">04 / Credentials</p>
                    <h2 class="display-heading reveal reveal-delay-1" id="credentials-title">A record of discipline.</h2>
                    <p class="reveal reveal-delay-2">Academic distinction and practical exposure underpin the way I approach every assignment: prepared, accountable, and attentive to detail.</p>
                </div>

                <div class="credential-list">
                    <article class="credential-item reveal">
                        <span>01</span>
                        <div>
                            <h3>Magna Cum Laude</h3>
                            <p>Bachelor of Arts in Political Science, University of Nueva Caceres, 2025</p>
                        </div>
                    </article>
                    <article class="credential-item reveal reveal-delay-1">
                        <span>02</span>
                        <div>
                            <h3>President's Lister</h3>
                            <p>Consistent recognition for academic performance throughout undergraduate study</p>
                        </div>
                    </article>
                    <article class="credential-item reveal reveal-delay-2">
                        <span>03</span>
                        <div>
                            <h3>Law Office Internship</h3>
                            <p>200 hours completed at the Provincial Prosecutor's Office, Camarines Sur, 2024</p>
                        </div>
                    </article>
                </div>
            </div>
        </section>

        <section class="contact" id="contact" aria-labelledby="contact-title">
            <div class="section-shell contact-layout">
                <div class="contact-copy">
                    <p class="section-kicker reveal">05 / Contact</p>
                    <h2 class="display-heading contact-heading reveal reveal-delay-1" id="contact-title">Let's make the next task <em>matter.</em></h2>
                    <p class="reveal reveal-delay-2">Open to full-time roles, legal assistance, freelance research, virtual operations, and thoughtful creative collaborations.</p>
                    <div class="contact-links reveal reveal-delay-3">
                        <a class="contact-link" href="mailto:ruelc2002@gmail.com">ruelc2002@gmail.com</a>
                        <span class="contact-location">Camarines Sur, Philippines / Available remotely</span>
                    </div>
                </div>

                <form class="contact-form reveal" id="contactForm" novalidate>
                    <h3 class="form-heading">Start a conversation</h3>
                    <div class="form-row">
                        <div class="form-field">
                            <label for="name">Your name</label>
                            <input id="name" name="name" type="text" autocomplete="name" placeholder="Jane Smith" required>
                        </div>
                        <div class="form-field">
                            <label for="email">Email address</label>
                            <input id="email" name="email" type="email" autocomplete="email" placeholder="jane@company.com" required>
                        </div>
                    </div>
                    <div class="form-field">
                        <label for="subject">Subject</label>
                        <input id="subject" name="subject" type="text" placeholder="A legal research opportunity" required>
                    </div>
                    <div class="form-field">
                        <label for="message">Project details</label>
                        <textarea id="message" name="message" placeholder="Tell me a little about the role, project, or timeline..." required></textarea>
                    </div>
                    <div class="form-footer">
                        <button class="button-primary" type="submit">
                            Send inquiry
                            <svg viewBox="0 0 20 20" fill="none" aria-hidden="true"><path d="M3 10h14M12 5l5 5-5 5" stroke="currentColor" stroke-width="1.5"/></svg>
                        </button>
                        <p class="form-status" id="formStatus" role="status" aria-live="polite">This opens your email app with the details prepared.</p>
                    </div>
                </form>
            </div>
        </section>
    </main>

    <footer class="site-footer">
        <div class="footer-inner">
            <span>&copy; <span id="currentYear">2025</span> Ruel Christian Salvino</span>
            <a href="#home">Back to top</a>
            <a href="https://www.pexels.com" target="_blank" rel="noreferrer">Placeholder imagery via Pexels</a>
        </div>
    </footer>

    <div class="project-modal" id="projectModal" role="dialog" aria-modal="true" aria-labelledby="modalTitle" aria-hidden="true">
        <div class="modal-panel">
            <img class="modal-image" id="modalImage" src="https://images.pexels.com/photos/7876093/pexels-photo-7876093.jpeg?auto=compress&cs=tinysrgb&fit=crop&h=1100&w=1000" alt="Legal workspace with documents and a Lady Justice statue">
            <div class="modal-content">
                <button class="modal-close" id="modalClose" type="button" aria-label="Close project details">&times;</button>
                <span class="modal-category" id="modalCategory"></span>
                <h2 class="modal-title" id="modalTitle"></h2>
                <p class="modal-description" id="modalDescription"></p>
                <div class="modal-detail"><strong>Focus</strong> <span id="modalFocus"></span></div>
                <div class="modal-detail"><strong>Tools</strong> <span id="modalTools"></span></div>
                <a class="button-primary" id="modalContact" href="#contact">
                    Request a sample
                    <svg viewBox="0 0 20 20" fill="none" aria-hidden="true"><path d="M3 10h14M12 5l5 5-5 5" stroke="currentColor" stroke-width="1.5"/></svg>
                </a>
            </div>
        </div>
    </div>

    <script>
        const body = document.body;
        const nav = document.getElementById("siteNav");
        const menuButton = document.getElementById("menuButton");
        const mobileMenu = document.getElementById("mobileMenu");
        const prefersReducedMotion = window.matchMedia("(prefers-reduced-motion: reduce)").matches;

        function setMenu(open) {
            body.classList.toggle("menu-open", open);
            menuButton.setAttribute("aria-expanded", String(open));
            menuButton.setAttribute("aria-label", open ? "Close navigation menu" : "Open navigation menu");
            mobileMenu.setAttribute("aria-hidden", String(!open));
            mobileMenu.inert = !open;
        }

        menuButton.addEventListener("click", () => setMenu(!body.classList.contains("menu-open")));
        mobileMenu.querySelectorAll("a").forEach((link) => link.addEventListener("click", () => setMenu(false)));

        function handleScroll() {
            nav.classList.toggle("scrolled", window.scrollY > 30);
        }

        handleScroll();
        window.addEventListener("scroll", handleScroll, { passive: true });

        const revealElements = document.querySelectorAll(".reveal");
        if ("IntersectionObserver" in window && !prefersReducedMotion) {
            const revealObserver = new IntersectionObserver((entries, observer) => {
                entries.forEach((entry) => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add("is-visible");
                        observer.unobserve(entry.target);
                    }
                });
            }, { threshold: 0.12, rootMargin: "0px 0px -40px" });
            revealElements.forEach((element) => revealObserver.observe(element));
        } else {
            revealElements.forEach((element) => element.classList.add("is-visible"));
        }

        const sectionLinks = document.querySelectorAll(".desktop-nav a");
        const observedSections = document.querySelectorAll("main section[id]");
        if ("IntersectionObserver" in window) {
            const sectionObserver = new IntersectionObserver((entries) => {
                entries.forEach((entry) => {
                    if (!entry.isIntersecting) return;
                    sectionLinks.forEach((link) => {
                        link.classList.toggle("active", link.getAttribute("href") === `#${entry.target.id}`);
                    });
                });
            }, { rootMargin: "-35% 0px -55%" });
            observedSections.forEach((section) => sectionObserver.observe(section));
        }

        const filterButtons = document.querySelectorAll(".filter-button");
        const projects = document.querySelectorAll(".project");

        filterButtons.forEach((button) => {
            button.addEventListener("click", () => {
                const filter = button.dataset.filter;
                filterButtons.forEach((item) => {
                    const selected = item === button;
                    item.classList.toggle("active", selected);
                    item.setAttribute("aria-pressed", String(selected));
                });

                projects.forEach((project) => {
                    const matches = filter === "all" || project.dataset.category === filter;
                    if (matches) {
                        project.hidden = false;
                        requestAnimationFrame(() => project.classList.remove("is-hiding"));
                    } else {
                        project.classList.add("is-hiding");
                        window.setTimeout(() => {
                            if (project.classList.contains("is-hiding")) project.hidden = true;
                        }, 360);
                    }
                });
            });
        });

        const projectData = {
            legal: {
                category: "Legal writing / Research",
                title: "Pleadings & Formal Briefs",
                description: "Academic and internship-informed legal documents shaped around clear issue framing, careful source review, and an organized presentation of facts and authorities.",
                focus: "Case review, legal synthesis, document assembly",
                tools: "Legal databases, Microsoft Word, Google Workspace",
                image: "https://images.pexels.com/photos/7876093/pexels-photo-7876093.jpeg?auto=compress&cs=tinysrgb&fit=crop&h=1100&w=1000",
                alt: "Legal workspace with documents and a Lady Justice statue"
            },
            design: {
                category: "Graphic design / Editorial",
                title: "Editorial Layout Systems",
                description: "Readable, repeatable visual systems for manuscripts, presentations, and campaign assets, balancing hierarchy and brand consistency with practical production needs.",
                focus: "Editorial hierarchy, templates, layout consistency",
                tools: "Canva, Google Slides, Microsoft Office",
                image: "https://images.pexels.com/photos/6143824/pexels-photo-6143824.jpeg?auto=compress&cs=tinysrgb&fit=crop&h=1100&w=1000",
                alt: "Editorial design magazine being reviewed on a desk"
            },
            video: {
                category: "Video editing / Social",
                title: "Social Video Campaigns",
                description: "Platform-ready edits designed for clarity and retention through purposeful pacing, accurate captions, clean transitions, and organized version delivery.",
                focus: "Short-form edits, subtitles, pacing, exports",
                tools: "CapCut, Premiere workflows, Canva",
                image: "https://images.pexels.com/photos/29505140/pexels-photo-29505140.jpeg?auto=compress&cs=tinysrgb&fit=crop&h=1100&w=1000",
                alt: "Professional video editing timeline on a monitor"
            }
        };

        const modal = document.getElementById("projectModal");
        const modalClose = document.getElementById("modalClose");
        const modalContact = document.getElementById("modalContact");
        let lastFocusedElement = null;

        function openModal(projectKey) {
            const project = projectData[projectKey];
            if (!project) return;
            lastFocusedElement = document.activeElement;
            document.getElementById("modalImage").src = project.image;
            document.getElementById("modalImage").alt = project.alt;
            document.getElementById("modalCategory").textContent = project.category;
            document.getElementById("modalTitle").textContent = project.title;
            document.getElementById("modalDescription").textContent = project.description;
            document.getElementById("modalFocus").textContent = project.focus;
            document.getElementById("modalTools").textContent = project.tools;
            modal.classList.add("open");
            modal.setAttribute("aria-hidden", "false");
            body.classList.add("modal-open");
            window.setTimeout(() => modalClose.focus(), 80);
        }

        function closeModal() {
            modal.classList.remove("open");
            modal.setAttribute("aria-hidden", "true");
            body.classList.remove("modal-open");
            if (lastFocusedElement) lastFocusedElement.focus();
        }

        document.querySelectorAll("[data-project]").forEach((button) => {
            button.addEventListener("click", () => openModal(button.dataset.project));
        });
        modalClose.addEventListener("click", closeModal);
        modalContact.addEventListener("click", closeModal);
        modal.addEventListener("click", (event) => {
            if (event.target === modal) closeModal();
        });

        document.addEventListener("keydown", (event) => {
            if (event.key === "Escape") {
                if (modal.classList.contains("open")) closeModal();
                if (body.classList.contains("menu-open")) setMenu(false);
            }
            if (event.key === "Tab" && modal.classList.contains("open")) {
                const focusable = modal.querySelectorAll("button, a[href]");
                const first = focusable[0];
                const last = focusable[focusable.length - 1];
                if (event.shiftKey && document.activeElement === first) {
                    event.preventDefault();
                    last.focus();
                } else if (!event.shiftKey && document.activeElement === last) {
                    event.preventDefault();
                    first.focus();
                }
            }
        });

        const contactForm = document.getElementById("contactForm");
        const formStatus = document.getElementById("formStatus");

        contactForm.addEventListener("submit", (event) => {
            event.preventDefault();
            if (!contactForm.checkValidity()) {
                contactForm.reportValidity();
                formStatus.textContent = "Please complete each field before sending.";
                return;
            }

            const formData = new FormData(contactForm);
            const subject = encodeURIComponent(formData.get("subject"));
            const message = encodeURIComponent(
                `Hello Ruel,\n\n${formData.get("message")}\n\nFrom: ${formData.get("name")}\nEmail: ${formData.get("email")}`
            );
            formStatus.textContent = "Your email app is opening with the message prepared.";
            window.location.href = `mailto:ruelc2002@gmail.com?subject=${subject}&body=${message}`;
        });

        document.getElementById("currentYear").textContent = new Date().getFullYear();

        if (!prefersReducedMotion) {
            const heroImage = document.getElementById("heroImage");
            const aboutImage = document.querySelector(".parallax-image");
            let ticking = false;

            window.addEventListener("scroll", () => {
                if (ticking) return;
                ticking = true;
                window.requestAnimationFrame(() => {
                    const y = window.scrollY;
                    if (y < window.innerHeight * 1.2) {
                        heroImage.style.transform = `translate3d(0, ${Math.min(y * 0.075, 55)}px, 0) scale(1.01)`;
                    }
                    const aboutRect = aboutImage.getBoundingClientRect();
                    if (aboutRect.top < window.innerHeight && aboutRect.bottom > 0) {
                        const offset = (window.innerHeight - aboutRect.top) * 0.035;
                        aboutImage.style.transform = `translate3d(0, ${Math.min(offset, 42)}px, 0) scale(1.02)`;
                    }
                    ticking = false;
                });
            }, { passive: true });
        }
    </script>
</body>
</html>
