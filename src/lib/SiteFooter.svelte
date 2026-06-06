<footer class="site-footer">
    <div class="social-links" aria-label="Social links">
        <a href="https://x.com/" class="social-link" aria-label="Twitter">
            <img src="/img/twitter-vector.svg" alt="" />
        </a>
        <a href="https://www.behance.net/" class="social-link" aria-label="Behance">
            <img src="/img/behance-vector.svg" alt="" />
        </a>
        <a href="mailto:hello@example.com" class="social-link" aria-label="Email">
            <img src="/img/mail-vector.svg" alt="" />
        </a>
    </div>
    <div class="footer-rule" aria-hidden="true"></div>
    <p class="copyright">©2023</p>
</footer>

<style>
    .site-footer {
        position: fixed;
        bottom: clamp(50px, 8.301vh, 85px);
        right: var(--page-gutter);
        left: var(--page-gutter);
        height: clamp(36px, 3.333vw, 40px);
    }

    .social-links,
    .social-link {
        display: flex;
    }

    .social-links {
        position: absolute;
        top: 0;
        left: 0;
        width: clamp(128px, 12.5vw, 150px);
        gap: clamp(10px, 1.25vw, 15px);
        align-items: flex-start;
    }

    .social-link {
        width: clamp(36px, 3.333vw, 40px);
        height: clamp(36px, 3.333vw, 40px);
        align-items: center;
        justify-content: center;
        border-radius: 9px;
        background: var(--button);
    }

    .social-link img {
        display: block;
        width: clamp(24.911px, 2.307vw, 27.679px);
        height: clamp(25.074px, 2.322vw, 27.86px);
        object-fit: contain;
    }

    .social-link[aria-label="Email"] img {
        height: clamp(20.372px, 1.886vw, 22.636px);
    }

    .footer-rule {
        position: absolute;
        top: 50%;
        right: clamp(84px, 7.958vw, 95.5px);
        left: clamp(148px, 14.125vw, 169.5px);
        height: 1px;
        background: var(--ink);
    }

    .copyright {
        position: absolute;
        top: 50%;
        right: 0;
        margin: 0;
        color: var(--ink);
        font-size: clamp(20px, 2vw, 24px);
        font-weight: 400;
        line-height: 1.013;
        white-space: nowrap;
        transform: translateY(-50%);
    }

    @media (max-width: 900px) {
        .site-footer {
            bottom: 48px;
        }
    }

    @media (max-width: 760px) {
        .site-footer {
            bottom: 32px;
        }
    }
</style>
