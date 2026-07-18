/* NextPath Blog — App Stylesheet */

/* Transitions and Global Styles */
.fade-in {
  animation: fadeIn 0.4s ease-out forwards;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(12px); }
  to { opacity: 1; transform: translateY(0); }
}

.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

/* Header & Nav */
.main-header {
  background-color: var(--color-bg);
  border-bottom: 1px solid var(--color-border);
  position: sticky;
  top: 0;
  z-index: 100;
  transition: var(--transition);
}

.header-inner {
  height: 80px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.logo-area {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.logo-dot {
  width: 10px;
  height: 10px;
  background-color: var(--color-primary);
  border-radius: 50%;
  margin-right: 8px;
}

.logo-text {
  font-family: var(--font-serif);
  font-size: 22px;
  font-weight: 700;
  color: var(--color-ink);
}

.logo-text .light {
  font-family: var(--font-sans);
  font-weight: 300;
  color: var(--color-accent);
}

.desktop-nav {
  display: flex;
  gap: 32px;
}

.nav-link {
  background: none;
  border: none;
  font-family: var(--font-sans);
  font-size: 16px;
  font-weight: 500;
  color: var(--color-meta);
  cursor: pointer;
  padding: 8px 0;
  position: relative;
  transition: var(--transition);
}

.nav-link:hover {
  color: var(--color-primary);
}

.nav-link.active {
  color: var(--color-primary);
}

.nav-link.active::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background-color: var(--color-primary);
}

.mobile-menu-btn {
  display: none;
  background: none;
  border: none;
  color: var(--color-ink);
  cursor: pointer;
}

/* Mobile Nav Overlay */
.mobile-nav-overlay {
  position: absolute;
  top: 80px;
  left: 0;
  width: 100%;
  background-color: var(--color-bg);
  border-bottom: 1px solid var(--color-border);
  box-shadow: var(--shadow-md);
  padding: 24px;
  animation: slideDown 0.3s ease-out;
}

@keyframes slideDown {
  from { transform: translateY(-10px); opacity: 0; }
  to { transform: translateY(0); opacity: 1; }
}

.mobile-nav {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.mobile-nav-link {
  background: none;
  border: none;
  text-align: left;
  font-family: var(--font-sans);
  font-size: 18px;
  font-weight: 500;
  color: var(--color-meta);
  padding: 8px 0;
  cursor: pointer;
  border-bottom: 1px solid rgba(27, 77, 62, 0.05);
}

.mobile-nav-link.active {
  color: var(--color-primary);
  border-bottom-color: var(--color-primary);
}

/* Main Content Layout */
.main-content {
  flex: 1;
}

/* Hero Section */
.hero-section {
  background-color: var(--color-bg-pale);
  padding: 96px 0 80px;
  text-align: center;
  transition: var(--transition);
}

.hero-badge {
  font-family: var(--font-mono);
  font-size: 13px;
  text-transform: uppercase;
  letter-spacing: 2px;
  color: var(--color-primary);
  margin-bottom: 16px;
  font-weight: 600;
}

.hero-title {
  font-size: 52px;
  color: var(--color-primary);
  max-width: 800px;
  margin: 0 auto 24px;
  letter-spacing: -1px;
}

.hero-subtitle {
  font-family: var(--font-sans);
  font-size: 20px;
  color: var(--color-meta);
  max-width: 600px;
  margin: 0 auto 36px;
  line-height: 1.5;
}

.hero-separator {
  width: 60px;
  height: 3px;
  background-color: var(--color-accent);
  margin: 0 auto;
}

/* Articles Grid Section */
.section-header {
  text-align: center;
  margin-bottom: 48px;
}

.section-title {
  font-size: 32px;
  color: var(--color-primary);
  margin-bottom: 8px;
}

.section-tagline {
  font-family: var(--font-mono);
  font-size: 13px;
  text-transform: uppercase;
  color: var(--color-accent);
  letter-spacing: 1px;
}

.articles-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 40px;
}

.no-posts-alert {
  text-align: center;
  color: var(--color-meta);
  font-style: italic;
  padding: 40px 0;
}

/* Blog Card Styles */
.blog-card {
  background-color: var(--color-bg);
  border: 1px solid var(--color-border);
  border-radius: var(--border-radius-lg);
  overflow: hidden;
  cursor: pointer;
  transition: var(--transition);
  display: flex;
  flex-direction: column;
}

.blog-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-md);
  border-color: var(--color-accent);
}

.blog-card-image-wrapper {
  position: relative;
  aspect-ratio: 16/9;
  overflow: hidden;
  background-color: var(--color-bg-pale);
}

.blog-card-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
}

.blog-card:hover .blog-card-image {
  transform: scale(1.05);
}

.blog-card-tags {
  position: absolute;
  bottom: 12px;
  left: 12px;
  display: flex;
  gap: 6px;
  flex-wrap: wrap;
}

.blog-card-tag {
  background-color: rgba(27, 77, 62, 0.85);
  color: white;
  font-family: var(--font-mono);
  font-size: 10px;
  padding: 4px 8px;
  border-radius: 4px;
  text-transform: uppercase;
  backdrop-filter: blur(4px);
}

.blog-card-content {
  padding: 24px;
  display: flex;
  flex-direction: column;
  flex: 1;
}

.blog-card-meta {
  display: flex;
  justify-content: space-between;
  font-family: var(--font-mono);
  font-size: 11px;
  color: var(--color-meta);
  margin-bottom: 12px;
}

.blog-card-date, .blog-card-likes-count {
  display: inline-flex;
  align-items: center;
}

.blog-card-title {
  font-size: 22px;
  color: var(--color-primary);
  margin-bottom: 8px;
  line-height: 1.3;
}

.blog-card-tagline {
  font-size: 15px;
  color: var(--color-meta);
  margin-bottom: 20px;
  flex: 1;
}

.blog-card-read-more {
  font-family: var(--font-mono);
  font-size: 12px;
  font-weight: bold;
  color: var(--color-primary);
  text-transform: uppercase;
  align-self: flex-start;
  transition: var(--transition);
}

.blog-card:hover .blog-card-read-more {
  color: var(--color-accent);
  padding-left: 4px;
}

/* Article View Page */
.article-container {
  max-width: 760px;
  padding-top: 40px;
  padding-bottom: 80px;
}

.back-link-btn {
  background: none;
  border: none;
  font-family: var(--font-sans);
  font-size: 15px;
  color: var(--color-meta);
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  margin-bottom: 32px;
  transition: var(--transition);
}

.back-link-btn:hover {
  color: var(--color-primary);
  transform: translateX(-4px);
}

.full-article {
  background-color: var(--color-bg);
}

.article-header {
  margin-bottom: 32px;
}

.article-tags {
  display: flex;
  gap: 8px;
  margin-bottom: 16px;
}

.article-tag {
  font-family: var(--font-mono);
  font-size: 11px;
  color: var(--color-primary);
  background-color: var(--color-bg-pale);
  padding: 4px 10px;
  border-radius: 4px;
  text-transform: uppercase;
}

.article-title {
  font-size: 42px;
  line-height: 1.15;
  color: var(--color-primary);
  margin-bottom: 16px;
}

.article-tagline-desc {
  font-size: 20px;
  line-height: 1.4;
  color: var(--color-meta);
  margin-bottom: 24px;
  font-style: italic;
}

.article-meta-info {
  font-family: var(--font-mono);
  font-size: 13px;
  color: var(--color-meta);
  border-bottom: 1px solid var(--color-border);
  padding-bottom: 16px;
}

.article-cover-image-wrapper {
  aspect-ratio: 16/9;
  border-radius: var(--border-radius-lg);
  overflow: hidden;
  margin-bottom: 40px;
  box-shadow: var(--shadow-sm);
}

.article-cover-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Editorial Blog Content Styling */
.blog-content {
  font-size: 18px;
  line-height: 1.75;
  color: var(--color-ink);
}

.blog-content p {
  margin-bottom: 24px;
}

.blog-content h2 {
  font-size: 28px;
  color: var(--color-primary);
  margin: 40px 0 16px;
}

.blog-content blockquote {
  font-family: var(--font-serif);
  font-size: 22px;
  line-height: 1.5;
  color: var(--color-primary);
  border-left: 4px solid var(--color-accent);
  padding-left: 24px;
  margin: 32px 0;
  font-style: italic;
  background-color: var(--color-bg-pale);
  padding: 24px;
  border-radius: 0 var(--border-radius) var(--border-radius) 0;
}

.blog-content ul, .blog-content ol {
  margin-left: 24px;
  margin-bottom: 24px;
}

.blog-content li {
  margin-bottom: 8px;
}

.blog-content a {
  text-decoration: underline;
  text-underline-offset: 4px;
  font-weight: 500;
}

.blog-content img {
  max-width: 100%;
  height: auto;
  border-radius: var(--border-radius);
  margin: 32px 0;
}

/* Dropcap for beautiful editorial design */
.blog-content .dropcap::first-letter {
  font-family: var(--font-serif);
  font-size: 3.5em;
  font-weight: 700;
  float: left;
  line-height: 0.85;
  margin: 6px 12px 0 0;
  color: var(--color-primary);
}

.article-actions-footer {
  border-top: 1px solid var(--color-border);
  border-bottom: 1px solid var(--color-border);
  padding: 24px 0;
  margin: 48px 0;
}

.article-like-btn {
  background-color: var(--color-bg-pale);
  border: 1px solid var(--color-border);
  color: var(--color-primary);
  padding: 12px 24px;
  border-radius: var(--border-radius);
  font-family: var(--font-sans);
  font-size: 15px;
  font-weight: 600;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  transition: var(--transition);
}

.article-like-btn:hover {
  background-color: var(--color-primary);
  color: white;
  border-color: var(--color-primary);
}

.article-like-btn.liked {
  background-color: var(--color-primary);
  color: white;
  border-color: var(--color-primary);
  cursor: default;
}

.article-loading {
  text-align: center;
  color: var(--color-meta);
  padding: 80px 0;
}

/* Comments Section */
.comments-section {
  margin-top: 48px;
}

.comments-header {
  display: flex;
  align-items: center;
  margin-bottom: 24px;
  color: var(--color-primary);
}

.comments-icon {
  margin-right: 10px;
}

.comments-header h3 {
  font-size: 20px;
}

.comment-form {
  background-color: var(--color-bg-pale);
  padding: 24px;
  border-radius: var(--border-radius-lg);
  margin-bottom: 32px;
}

.form-group {
  margin-bottom: 16px;
}

.comment-input, .comment-textarea {
  width: 100%;
  padding: 12px 16px;
  border: 1px solid var(--color-border);
  border-radius: var(--border-radius);
  background-color: var(--color-bg);
  color: var(--color-ink);
  font-size: 15px;
  transition: var(--transition);
}

.comment-input:focus, .comment-textarea:focus {
  outline: none;
  border-color: var(--color-primary);
  box-shadow: 0 0 0 2px rgba(27, 77, 62, 0.1);
}

.comment-textarea {
  resize: vertical;
}

.comment-form-actions {
  display: flex;
  justify-content: flex-end;
}

.comment-submit-btn {
  background-color: var(--color-primary);
  color: white;
  border: none;
  padding: 12px 24px;
  border-radius: var(--border-radius);
  font-size: 14px;
  font-weight: 600;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  transition: var(--transition);
}

.comment-submit-btn:hover:not(:disabled) {
  background-color: var(--color-accent);
}

.comment-submit-btn:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}

.status-banner {
  margin-top: 16px;
  padding: 12px 16px;
  border-radius: var(--border-radius);
  font-size: 14px;
}

.status-banner.success {
  background-color: rgba(79, 168, 130, 0.15);
  color: #1b734c;
  border: 1px solid rgba(79, 168, 130, 0.3);
}

.status-banner.error {
  background-color: rgba(220, 38, 38, 0.1);
  color: #b91c1c;
  border: 1px solid rgba(220, 38, 38, 0.2);
}

.local-mode-alert {
  display: flex;
  align-items: center;
  gap: 8px;
  font-family: var(--font-mono);
  font-size: 11px;
  color: #d97706;
  background-color: #fef3c7;
  padding: 8px 12px;
  border-radius: var(--border-radius);
  margin-bottom: 24px;
}

.comments-list {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.no-comments {
  text-align: center;
  color: var(--color-meta);
  font-style: italic;
  padding: 24px 0;
}

.comment-item {
  border-bottom: 1px solid var(--color-border);
  padding-bottom: 20px;
}

.comment-item:last-child {
  border-bottom: none;
}

.comment-meta {
  display: flex;
  justify-content: space-between;
  margin-bottom: 8px;
}

.comment-author {
  font-weight: 600;
  color: var(--color-primary);
  font-size: 15px;
}

.comment-date {
  font-family: var(--font-mono);
  font-size: 11px;
  color: var(--color-meta);
}

.comment-content {
  font-size: 15px;
  line-height: 1.5;
  color: var(--color-ink);
  white-space: pre-wrap;
}

/* About Page */
.narrow-container {
  max-width: 640px;
}

.about-card {
  background-color: var(--color-bg-pale);
  padding: 48px;
  border-radius: var(--border-radius-lg);
  border: 1px solid var(--color-border);
  text-align: center;
}

.about-icon-wrapper {
  width: 64px;
  height: 64px;
  background-color: var(--color-primary);
  color: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 24px;
}

.about-title {
  font-size: 32px;
  color: var(--color-primary);
  margin-bottom: 24px;
}

.about-main-text {
  font-size: 18px;
  line-height: 1.7;
  color: var(--color-ink);
}

.about-divider {
  width: 80px;
  height: 1px;
  background-color: var(--color-border);
  margin: 32px auto;
}

.socials-title {
  font-family: var(--font-serif);
  font-size: 20px;
  color: var(--color-primary);
  margin-bottom: 24px;
}

.social-links-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}

@media (max-width: 480px) {
  .social-links-grid {
    grid-template-columns: 1fr;
  }
}

.social-link-item {
  display: flex;
  align-items: center;
  background-color: var(--color-bg);
  border: 1px solid var(--color-border);
  padding: 16px;
  border-radius: var(--border-radius);
  text-align: left;
  transition: var(--transition);
}

.social-link-item:hover {
  border-color: var(--color-primary);
  transform: translateY(-2px);
  box-shadow: var(--shadow-sm);
}

.social-link-item svg {
  color: var(--color-primary);
  flex-shrink: 0;
}

.social-link-meta {
  margin-left: 12px;
  display: flex;
  flex-direction: column;
}

.social-platform {
  font-size: 12px;
  font-family: var(--font-mono);
  color: var(--color-meta);
  text-transform: uppercase;
}

.social-handle {
  font-size: 14px;
  font-weight: 600;
  color: var(--color-primary);
}

/* Contact Page */
.contact-card {
  background-color: var(--color-bg);
  border: 1px solid var(--color-border);
  padding: 48px;
  border-radius: var(--border-radius-lg);
  box-shadow: var(--shadow-sm);
}

.contact-title {
  font-size: 32px;
  color: var(--color-primary);
  margin-bottom: 12px;
}

.contact-subtitle {
  color: var(--color-meta);
  font-size: 16px;
  margin-bottom: 32px;
}

.contact-input, .contact-textarea {
  width: 100%;
  padding: 12px 16px;
  border: 1px solid var(--color-border);
  border-radius: var(--border-radius);
  background-color: var(--color-input-bg);
  color: var(--color-ink);
  font-size: 15px;
  transition: var(--transition);
}

.contact-input:focus, .contact-textarea:focus {
  outline: none;
  border-color: var(--color-primary);
  background-color: var(--color-bg);
  box-shadow: 0 0 0 2px rgba(27, 77, 62, 0.1);
}

.contact-textarea {
  resize: vertical;
}

.contact-submit-btn {
  background-color: var(--color-primary);
  color: white;
  border: none;
  padding: 14px 28px;
  border-radius: var(--border-radius);
  font-size: 15px;
  font-weight: 600;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  transition: var(--transition);
  margin-top: 12px;
}

.contact-submit-btn:hover {
  background-color: var(--color-accent);
}

.contact-success-banner {
  display: flex;
  background-color: rgba(79, 168, 130, 0.1);
  border: 1px solid rgba(79, 168, 130, 0.3);
  color: var(--color-primary);
  padding: 24px;
  border-radius: var(--border-radius);
  align-items: flex-start;
}

/* Footer styling */
.main-footer {
  background-color: var(--color-primary);
  color: white;
  padding: 48px 0;
  margin-top: auto;
  border-top: 1px solid var(--color-border);
}

.footer-inner {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 16px;
  text-align: center;
}

.footer-logo {
  display: flex;
  align-items: center;
  font-family: var(--font-serif);
  font-size: 20px;
  font-weight: bold;
}

.footer-logo .logo-dot {
  background-color: var(--color-accent);
}

.footer-copyright {
  font-size: 14px;
  opacity: 0.8;
}

/* Back to Top button */
.scroll-top-btn {
  position: fixed;
  bottom: 24px;
  right: 24px;
  background-color: var(--color-primary);
  color: white;
  border: none;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  box-shadow: var(--shadow-md);
  transition: var(--transition);
  z-index: 50;
}

.scroll-top-btn:hover {
  background-color: var(--color-accent);
  transform: translateY(-2px);
}

/* SECRET ADMIN PANEL MODAL */
.admin-panel-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgba(17, 26, 20, 0.65);
  backdrop-filter: blur(4px);
  z-index: 1000;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 40px;
}

@media (max-width: 768px) {
  .admin-panel-overlay {
    padding: 10px;
  }
}

.admin-panel-container {
  background-color: var(--color-bg);
  border: 1px solid var(--color-border);
  border-radius: var(--border-radius-lg);
  width: 100%;
  max-width: 900px;
  max-height: 90vh;
  display: flex;
  flex-direction: column;
  box-shadow: var(--shadow-lg);
  overflow: hidden;
  animation: modalEnter 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

@keyframes modalEnter {
  from { opacity: 0; transform: scale(0.95); }
  to { opacity: 1; transform: scale(1); }
}

.admin-header {
  padding: 24px 32px;
  border-bottom: 1px solid var(--color-border);
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: var(--color-bg-pale);
}

.admin-title-area h2 {
  font-size: 22px;
  color: var(--color-primary);
}

.admin-badge {
  font-family: var(--font-mono);
  font-size: 10px;
  background-color: var(--color-primary);
  color: white;
  padding: 2px 8px;
  border-radius: 4px;
  text-transform: uppercase;
}

.admin-close-btn {
  background: none;
  border: none;
  color: var(--color-primary);
  cursor: pointer;
  transition: var(--transition);
  padding: 4px;
  border-radius: 50%;
}

.admin-close-btn:hover {
  background-color: rgba(27, 77, 62, 0.1);
}

.admin-posts-list-view {
  padding: 32px;
  overflow-y: auto;
  flex: 1;
}

.admin-list-actions {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 24px;
}

.btn-create-post {
  background-color: var(--color-primary);
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: var(--border-radius);
  font-size: 14px;
  font-weight: 600;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  transition: var(--transition);
}

.btn-create-post:hover {
  background-color: var(--color-accent);
}

.admin-table-container {
  border: 1px solid var(--color-border);
  border-radius: var(--border-radius);
  overflow: hidden;
}

.admin-table {
  width: 100%;
  border-collapse: collapse;
  text-align: left;
  font-size: 14px;
}

.admin-table th, .admin-table td {
  padding: 16px 20px;
  border-bottom: 1px solid var(--color-border);
}

.admin-table th {
  background-color: var(--color-bg-pale);
  font-weight: 600;
  color: var(--color-primary);
  font-family: var(--font-mono);
  text-transform: uppercase;
  font-size: 11px;
}

.admin-table tr:last-child td {
  border-bottom: none;
}

.post-title-cell {
  display: flex;
  flex-direction: column;
}

.post-title-cell strong {
  font-size: 15px;
  color: var(--color-ink);
}

.post-tagline-sub {
  font-size: 12px;
  color: var(--color-meta);
}

.post-date-cell, .post-likes-cell {
  font-family: var(--font-mono);
  color: var(--color-meta);
}

.post-actions-cell {
  display: flex;
  gap: 8px;
}

.btn-action-edit, .btn-action-delete {
  background: none;
  border: 1px solid var(--color-border);
  padding: 6px;
  border-radius: 4px;
  cursor: pointer;
  transition: var(--transition);
  color: var(--color-meta);
}

.btn-action-edit:hover {
  border-color: var(--color-primary);
  color: var(--color-primary);
  background-color: var(--color-bg-pale);
}

.btn-action-delete:hover {
  border-color: #dc2626;
  color: #dc2626;
  background-color: rgba(220, 38, 38, 0.05);
}

/* Rich Text Editor Form Styles */
.admin-form {
  padding: 32px;
  overflow-y: auto;
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.form-heading {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid var(--color-border);
  padding-bottom: 16px;
}

.btn-secondary {
  background: none;
  border: 1px solid var(--color-border);
  color: var(--color-primary);
  padding: 8px 16px;
  border-radius: var(--border-radius);
  font-size: 14px;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  transition: var(--transition);
}

.btn-secondary:hover {
  background-color: var(--color-bg-pale);
}

.admin-form-grid {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.form-label {
  display: block;
  font-weight: 600;
  font-size: 14px;
  margin-bottom: 6px;
  color: var(--color-primary);
}

.admin-input {
  width: 100%;
  padding: 10px 14px;
  border: 1px solid var(--color-border);
  border-radius: var(--border-radius);
  background-color: var(--color-input-bg);
  color: var(--color-ink);
  font-size: 14px;
}

.admin-input:focus {
  outline: none;
  border-color: var(--color-primary);
}

.form-group-row {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 16px;
}

@media (max-width: 640px) {
  .form-group-row {
    grid-template-columns: 1fr;
  }
}

/* Rich Text Editor Inner Styles */
.rte-container {
  border: 1px solid var(--color-border);
  border-radius: var(--border-radius);
  overflow: hidden;
  background-color: var(--color-bg);
}

.rte-toolbar {
  background-color: var(--color-bg-pale);
  border-bottom: 1px solid var(--color-border);
  padding: 8px 16px;
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  gap: 8px;
}

.rte-tab {
  background: none;
  border: none;
  font-size: 13px;
  font-weight: 600;
  color: var(--color-meta);
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  gap: 4px;
  padding: 4px 8px;
  border-radius: 4px;
}

.rte-tab.active {
  color: var(--color-primary);
  background-color: var(--color-bg);
  box-shadow: var(--shadow-sm);
}

.rte-separator {
  width: 1px;
  height: 20px;
  background-color: var(--color-border);
  margin: 0 4px;
}

.rte-actions {
  display: flex;
  gap: 4px;
}

.rte-actions button {
  background: none;
  border: none;
  padding: 6px;
  border-radius: 4px;
  cursor: pointer;
  color: var(--color-primary);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: var(--transition);
}

.rte-actions button:hover {
  background-color: var(--color-bg);
}

.rte-textarea {
  width: 100%;
  padding: 16px;
  border: none;
  resize: vertical;
  background-color: var(--color-bg);
  color: var(--color-ink);
  font-family: var(--font-mono);
  font-size: 13px;
  line-height: 1.5;
  outline: none;
}

.rte-preview {
  padding: 24px;
  max-height: 400px;
  overflow-y: auto;
  background-color: var(--color-bg);
}

.rte-help {
  display: flex;
  align-items: center;
  gap: 6px;
  padding: 8px 16px;
  background-color: var(--color-bg-pale);
  border-top: 1px solid var(--color-border);
  font-size: 11px;
  color: var(--color-meta);
}

.rte-help code {
  font-family: var(--font-mono);
  background-color: rgba(27, 77, 62, 0.08);
  padding: 2px 4px;
  border-radius: 2px;
}

.form-submit-actions {
  display: flex;
  justify-content: flex-end;
  gap: 12px;
  border-top: 1px solid var(--color-border);
  padding-top: 24px;
}

.btn-cancel {
  background: none;
  border: 1px solid var(--color-border);
  color: var(--color-meta);
  padding: 12px 24px;
  border-radius: var(--border-radius);
  font-size: 14px;
  cursor: pointer;
  transition: var(--transition);
}

.btn-cancel:hover {
  background-color: var(--color-bg-pale);
  color: var(--color-primary);
}

.btn-save {
  background-color: var(--color-primary);
  color: white;
  border: none;
  padding: 12px 24px;
  border-radius: var(--border-radius);
  font-size: 14px;
  font-weight: 600;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  transition: var(--transition);
}

.btn-save:hover {
  background-color: var(--color-accent);
}

/* RESPONSIVE BREAKPOINTS */
@media (max-width: 768px) {
  .hero-title {
    font-size: 36px;
  }
  .hero-subtitle {
    font-size: 16px;
  }
  .articles-grid {
    grid-template-columns: 1fr;
    gap: 24px;
  }
  .article-title {
    font-size: 32px;
  }
  .about-card, .contact-card {
    padding: 24px;
  }
  .desktop-nav {
    display: none;
  }
  .mobile-menu-btn {
    display: block;
  }
  .admin-panel-overlay {
    padding: 0;
  }
  .admin-panel-container {
    max-height: 100vh;
    border-radius: 0;
  }
  .admin-posts-list-view, .admin-form {
    padding: 16px;
  }
}
