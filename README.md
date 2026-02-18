<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Repository - GitHub</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-primary: #0d1117;
            --bg-secondary: #161b22;
            --bg-tertiary: #21262d;
            --border-color: #30363d;
            --text-primary: #c9d1d9;
            --text-secondary: #8b949e;
            --text-link: #58a6ff;
            --accent-green: #238636;
            --accent-green-hover: #2ea043;
            --accent-blue: #1f6feb;
            --accent-purple: #8957e5;
            --accent-orange: #d29922;
            --accent-red: #f85149;
            --star-color: #e3b341;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans', Helvetica, Arial, sans-serif;
            background-color: var(--bg-primary);
            color: var(--text-primary);
            line-height: 1.5;
        }

        /* Header Styles */
        .header {
            background-color: var(--bg-secondary);
            border-bottom: 1px solid var(--border-color);
            padding: 16px 32px;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-content {
            max-width: 1280px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .logo {
            font-size: 32px;
            color: #fff;
        }

        .search-bar {
            flex: 1;
            max-width: 720px;
            margin: 0 16px;
            position: relative;
        }

        .search-bar input {
            width: 100%;
            padding: 8px 12px;
            background-color: var(--bg-primary);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            color: var(--text-primary);
            font-size: 14px;
            transition: all 0.2s;
        }

        .search-bar input:focus {
            outline: none;
            border-color: var(--text-link);
            box-shadow: 0 0 0 3px rgba(88, 166, 255, 0.3);
        }

        .header-nav {
            display: flex;
            align-items: center;
            gap: 16px;
        }

        .header-nav a {
            color: var(--text-primary);
            text-decoration: none;
            font-size: 14px;
            font-weight: 600;
            padding: 8px 12px;
            border-radius: 6px;
            transition: background-color 0.2s;
        }

        .header-nav a:hover {
            background-color: var(--bg-tertiary);
        }

        .notification-btn, .create-btn {
            background: none;
            border: 1px solid var(--border-color);
            color: var(--text-primary);
            padding: 8px 12px;
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.2s;
        }

        .notification-btn:hover, .create-btn:hover {
            background-color: var(--bg-tertiary);
            border-color: var(--text-secondary);
        }

        .avatar {
            width: 32px;
            height: 32px;
            border-radius: 50%;
            cursor: pointer;
            transition: opacity 0.2s;
        }

        .avatar:hover {
            opacity: 0.8;
        }

        /* Main Container */
        .main-container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 24px 32px;
        }

        /* Repository Header */
        .repo-header {
            margin-bottom: 16px;
            animation: fadeInUp 0.5s ease;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .repo-title {
            display: flex;
            align-items: center;
            gap: 8px;
            flex-wrap: wrap;
        }

        .repo-icon {
            color: var(--text-secondary);
            font-size: 18px;
        }

        .repo-owner {
            color: var(--text-link);
            text-decoration: none;
            font-size: 20px;
            font-weight: 600;
        }

        .repo-owner:hover {
            text-decoration: underline;
        }

        .repo-separator {
            color: var(--text-secondary);
            font-size: 20px;
        }

        .repo-name {
            color: var(--text-link);
            text-decoration: none;
            font-size: 20px;
            font-weight: 700;
        }

        .repo-name:hover {
            text-decoration: underline;
        }

        .visibility-badge {
            padding: 2px 8px;
            border: 1px solid var(--border-color);
            border-radius: 16px;
            font-size: 12px;
            color: var(--text-secondary);
            font-weight: 500;
        }

        .repo-actions {
            display: flex;
            gap: 8px;
            margin-top: 16px;
        }

        .action-btn {
            display: flex;
            align-items: center;
            gap: 6px;
            padding: 5px 12px;
            background-color: var(--bg-tertiary);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            color: var(--text-primary);
            font-size: 12px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
            position: relative;
        }

        .action-btn:hover {
            background-color: var(--border-color);
            border-color: var(--text-secondary);
        }

        .action-btn.starred {
            background-color: var(--bg-tertiary);
            border-color: var(--star-color);
        }

        .action-btn.starred .fa-star {
            color: var(--star-color);
        }

        .action-count {
            padding: 5px 10px;
            background-color: var(--bg-tertiary);
            border: 1px solid var(--border-color);
            border-left: none;
            border-radius: 0 6px 6px 0;
            font-size: 12px;
            font-weight: 600;
        }

        .action-btn.with-count {
            border-radius: 6px 0 0 6px;
        }

        .dropdown-arrow {
            margin-left: 4px;
        }

        /* Tabs Navigation */
        .tabs-nav {
            display: flex;
            border-bottom: 1px solid var(--border-color);
            margin-bottom: 24px;
            overflow-x: auto;
            animation: fadeIn 0.5s ease 0.1s both;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .tab-item {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 12px 16px;
            color: var(--text-secondary);
            text-decoration: none;
            font-size: 14px;
            font-weight: 500;
            border-bottom: 2px solid transparent;
            transition: all 0.2s;
            white-space: nowrap;
        }

        .tab-item:hover {
            color: var(--text-primary);
            background-color: var(--bg-secondary);
        }

        .tab-item.active {
            color: var(--text-primary);
            border-bottom-color: #f78166;
        }

        .tab-count {
            background-color: var(--bg-tertiary);
            padding: 2px 8px;
            border-radius: 16px;
            font-size: 12px;
        }

        /* Main Content Layout */
        .content-wrapper {
            display: grid;
            grid-template-columns: 1fr 320px;
            gap: 24px;
            animation: fadeInUp 0.5s ease 0.2s both;
        }

        @media (max-width: 1012px) {
            .content-wrapper {
                grid-template-columns: 1fr;
            }
        }

        /* Left Content */
        .main-content {
            min-width: 0;
        }

        /* Branch Selector and Actions */
        .file-navigation {
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 16px;
            margin-bottom: 16px;
        }

        .branch-selector {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .branch-btn {
            display: flex;
            align-items: center;
            gap: 6px;
            padding: 5px 12px;
            background-color: var(--bg-tertiary);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            color: var(--text-primary);
            font-size: 14px;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.2s;
        }

        .branch-btn:hover {
            background-color: var(--border-color);
        }

        .branch-info {
            display: flex;
            align-items: center;
            gap: 16px;
        }

        .branch-info a {
            color: var(--text-secondary);
            text-decoration: none;
            font-size: 14px;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .branch-info a:hover {
            color: var(--text-link);
        }

        .branch-info strong {
            color: var(--text-primary);
        }

        .code-actions {
            display: flex;
            gap: 8px;
        }

        .add-file-btn {
            display: flex;
            align-items: center;
            gap: 6px;
            padding: 5px 12px;
            background-color: var(--bg-tertiary);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            color: var(--text-primary);
            font-size: 14px;
            cursor: pointer;
            transition: all 0.2s;
        }

        .add-file-btn:hover {
            background-color: var(--border-color);
        }

        .code-btn {
            display: flex;
            align-items: center;
            gap: 6px;
            padding: 5px 16px;
            background-color: var(--accent-green);
            border: 1px solid var(--accent-green);
            border-radius: 6px;
            color: #fff;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
        }

        .code-btn:hover {
            background-color: var(--accent-green-hover);
        }

        /* Latest Commit */
        .latest-commit {
            display: flex;
            align-items: center;
            padding: 12px 16px;
            background-color: var(--bg-secondary);
            border: 1px solid var(--border-color);
            border-radius: 6px 6px 0 0;
            gap: 12px;
        }

        .commit-avatar {
            width: 24px;
            height: 24px;
            border-radius: 50%;
        }

        .commit-author {
            color: var(--text-primary);
            text-decoration: none;
            font-weight: 600;
            font-size: 14px;
        }

        .commit-author:hover {
            text-decoration: underline;
        }

        .commit-message {
            color: var(--text-secondary);
            font-size: 14px;
            flex: 1;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
        }

        .commit-message a {
            color: var(--text-secondary);
            text-decoration: none;
        }

        .commit-message a:hover {
            color: var(--text-link);
            text-decoration: underline;
        }

        .commit-sha {
            color: var(--text-link);
            text-decoration: none;
            font-size: 12px;
            font-family: monospace;
        }

        .commit-sha:hover {
            text-decoration: underline;
        }

        .commit-time {
            color: var(--text-secondary);
            font-size: 14px;
        }

        .commit-count {
            display: flex;
            align-items: center;
            gap: 4px;
            color: var(--text-secondary);
            font-size: 14px;
        }

        .commit-count a {
            color: var(--text-secondary);
            text-decoration: none;
        }

        .commit-count a:hover {
            color: var(--text-link);
        }

        /* File Explorer */
        .file-explorer {
            border: 1px solid var(--border-color);
            border-top: none;
            border-radius: 0 0 6px 6px;
            overflow: hidden;
        }

        .file-item {
            display: flex;
            align-items: center;
            padding: 8px 16px;
            border-bottom: 1px solid var(--border-color);
            transition: background-color 0.15s;
            cursor: pointer;
        }

        .file-item:last-child {
            border-bottom: none;
        }

        .file-item:hover {
            background-color: var(--bg-secondary);
        }

        .file-icon {
            width: 24px;
            margin-right: 8px;
            color: var(--text-secondary);
            font-size: 16px;
        }

        .file-icon.folder {
            color: var(--text-link);
        }

        .file-name {
            flex: 1;
            color: var(--text-primary);
            text-decoration: none;
            font-size: 14px;
        }

        .file-name:hover {
            text-decoration: underline;
            color: var(--text-link);
        }

        .file-commit {
            flex: 2;
            color: var(--text-secondary);
            font-size: 14px;
            padding: 0 16px;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
        }

        .file-commit a {
            color: var(--text-secondary);
            text-decoration: none;
        }

        .file-commit a:hover {
            color: var(--text-link);
            text-decoration: underline;
        }

        .file-time {
            color: var(--text-secondary);
            font-size: 14px;
            white-space: nowrap;
        }

        /* README Section */
        .readme-section {
            margin-top: 24px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            animation: fadeInUp 0.5s ease 0.3s both;
        }

        .readme-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 12px 16px;
            background-color: var(--bg-secondary);
            border-bottom: 1px solid var(--border-color);
        }

        .readme-title {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 14px;
            font-weight: 600;
        }

        .readme-actions {
            display: flex;
            gap: 8px;
        }

        .readme-action-btn {
            background: none;
            border: none;
            color: var(--text-secondary);
            cursor: pointer;
            padding: 4px 8px;
            border-radius: 4px;
            transition: all 0.2s;
        }

        .readme-action-btn:hover {
            color: var(--text-link);
            background-color: var(--bg-tertiary);
        }

        .readme-content {
            padding: 24px 32px;
        }

        .readme-content h1 {
            font-size: 32px;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 12px;
            margin-bottom: 16px;
        }

        .readme-content h2 {
            font-size: 24px;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 8px;
            margin: 24px 0 16px;
        }

        .readme-content p {
            margin-bottom: 16px;
            color: var(--text-primary);
        }

        .readme-content code {
            background-color: var(--bg-tertiary);
            padding: 2px 6px;
            border-radius: 4px;
            font-family: monospace;
            font-size: 13px;
        }

        .readme-content pre {
            background-color: var(--bg-secondary);
            padding: 16px;
            border-radius: 6px;
            overflow-x: auto;
            margin-bottom: 16px;
        }

        .readme-content pre code {
            background: none;
            padding: 0;
        }

        .readme-content ul, .readme-content ol {
            margin-left: 24px;
            margin-bottom: 16px;
        }

        .readme-content li {
            margin-bottom: 8px;
        }

        .readme-content a {
            color: var(--text-link);
            text-decoration: none;
        }

        .readme-content a:hover {
            text-decoration: underline;
        }

        .readme-content img {
            max-width: 100%;
            border-radius: 6px;
        }

        .badge-container {
            display: flex;
            gap: 8px;
            flex-wrap: wrap;
            margin-bottom: 16px;
        }

        .badge {
            display: inline-block;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 12px;
            font-weight: 600;
        }

        .badge-green {
            background-color: rgba(35, 134, 54, 0.3);
            color: #3fb950;
        }

        .badge-blue {
            background-color: rgba(31, 111, 235, 0.3);
            color: #58a6ff;
        }

        .badge-purple {
            background-color: rgba(137, 87, 229, 0.3);
            color: #a371f7;
        }

        /* Sidebar */
        .sidebar {
            animation: fadeInUp 0.5s ease 0.3s both;
        }

        .sidebar-section {
            padding-bottom: 16px;
            border-bottom: 1px solid var(--border-color);
            margin-bottom: 16px;
        }

        .sidebar-section:last-child {
            border-bottom: none;
        }

        .sidebar-header {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 12px;
        }

        .sidebar-title {
            font-size: 14px;
            font-weight: 600;
            color: var(--text-primary);
        }

        .sidebar-action {
            background: none;
            border: none;
            color: var(--text-secondary);
            cursor: pointer;
            transition: color 0.2s;
        }

        .sidebar-action:hover {
            color: var(--text-link);
        }

        /* About Section */
        .about-description {
            color: var(--text-primary);
            font-size: 14px;
            margin-bottom: 16px;
            line-height: 1.6;
        }

        .about-link {
            display: flex;
            align-items: center;
            gap: 8px;
            color: var(--text-link);
            text-decoration: none;
            font-size: 14px;
            margin-bottom: 8px;
        }

        .about-link:hover {
            text-decoration: underline;
        }

        .about-meta {
            display: flex;
            flex-direction: column;
            gap: 8px;
            margin-top: 16px;
        }

        .meta-item {
            display: flex;
            align-items: center;
            gap: 8px;
            color: var(--text-secondary);
            font-size: 14px;
        }

        .meta-item a {
            color: var(--text-link);
            text-decoration: none;
        }

        .meta-item a:hover {
            text-decoration: underline;
        }

        /* Topics */
        .topics {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .topic-tag {
            padding: 4px 10px;
            background-color: rgba(56, 139, 253, 0.15);
            color: var(--text-link);
            border-radius: 16px;
            font-size: 12px;
            text-decoration: none;
            transition: all 0.2s;
        }

        .topic-tag:hover {
            background-color: rgba(56, 139, 253, 0.3);
        }

        /* Stats Row */
        .stats-row {
            display: flex;
            gap: 16px;
            flex-wrap: wrap;
        }

        .stat-item {
            display: flex;
            align-items: center;
            gap: 6px;
            color: var(--text-secondary);
            font-size: 14px;
            text-decoration: none;
            transition: color 0.2s;
        }

        .stat-item:hover {
            color: var(--text-link);
        }

        .stat-item strong {
            color: var(--text-primary);
        }

        /* Releases */
        .release-item {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 12px;
            background-color: var(--bg-secondary);
            border-radius: 6px;
            margin-bottom: 8px;
            transition: background-color 0.2s;
        }

        .release-item:hover {
            background-color: var(--bg-tertiary);
        }

        .release-icon {
            color: var(--accent-green);
            font-size: 24px;
        }

        .release-info h4 {
            font-size: 14px;
            margin-bottom: 4px;
        }

        .release-info h4 a {
            color: var(--text-link);
            text-decoration: none;
        }

        .release-info h4 a:hover {
            text-decoration: underline;
        }

        .release-tag {
            display: inline-block;
            padding: 2px 8px;
            background-color: var(--accent-green);
            color: #fff;
            border-radius: 16px;
            font-size: 11px;
            font-weight: 600;
            margin-left: 8px;
        }

        .release-meta {
            font-size: 12px;
            color: var(--text-secondary);
        }

        /* Contributors */
        .contributors-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .contributor-avatar {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            transition: transform 0.2s;
            cursor: pointer;
        }

        .contributor-avatar:hover {
            transform: scale(1.1);
        }

        /* Languages */
        .language-bar {
            height: 8px;
            border-radius: 4px;
            overflow: hidden;
            display: flex;
            margin-bottom: 12px;
        }

        .language-segment {
            height: 100%;
            transition: opacity 0.2s;
            cursor: pointer;
        }

        .language-segment:hover {
            opacity: 0.8;
        }

        .language-list {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
        }

        .language-item {
            display: flex;
            align-items: center;
            gap: 6px;
            font-size: 12px;
            color: var(--text-secondary);
            cursor: pointer;
            transition: color 0.2s;
        }

        .language-item:hover {
            color: var(--text-primary);
        }

        .language-dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
        }

        /* Code Dropdown Modal */
        .code-dropdown {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            display: none;
            justify-content: center;
            align-items: flex-start;
            padding-top: 100px;
            z-index: 200;
        }

        .code-dropdown.active {
            display: flex;
        }

        .code-dropdown-content {
            background-color: var(--bg-secondary);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            width: 360px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
            animation: dropdownSlide 0.2s ease;
        }

        @keyframes dropdownSlide {
            from {
                opacity: 0;
                transform: translateY(-10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .dropdown-header {
            display: flex;
            padding: 12px;
            border-bottom: 1px solid var(--border-color);
            gap: 4px;
        }

        .dropdown-tab {
            padding: 8px 16px;
            background: none;
            border: none;
            color: var(--text-secondary);
            font-size: 14px;
            cursor: pointer;
            border-radius: 6px;
            transition: all 0.2s;
        }

        .dropdown-tab.active {
            background-color: var(--bg-tertiary);
            color: var(--text-primary);
        }

        .dropdown-tab:hover:not(.active) {
            color: var(--text-primary);
        }

        .dropdown-body {
            padding: 16px;
        }

        .clone-section {
            margin-bottom: 16px;
        }

        .clone-section h4 {
            font-size: 13px;
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .clone-url {
            display: flex;
            background-color: var(--bg-primary);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            overflow: hidden;
        }

        .clone-url input {
            flex: 1;
            padding: 8px 12px;
            background: none;
            border: none;
            color: var(--text-primary);
            font-size: 12px;
            font-family: monospace;
        }

        .clone-url input:focus {
            outline: none;
        }

        .clone-url button {
            padding: 8px 12px;
            background-color: var(--bg-tertiary);
            border: none;
            border-left: 1px solid var(--border-color);
            color: var(--text-secondary);
            cursor: pointer;
            transition: all 0.2s;
        }

        .clone-url button:hover {
            color: var(--text-primary);
            background-color: var(--border-color);
        }

        .dropdown-actions {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .dropdown-action-btn {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 8px 12px;
            background-color: var(--bg-tertiary);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            color: var(--text-primary);
            font-size: 14px;
            cursor: pointer;
            transition: all 0.2s;
            text-decoration: none;
        }

        .dropdown-action-btn:hover {
            background-color: var(--border-color);
        }

        /* Activity Graph */
        .activity-graph {
            margin-top: 16px;
        }

        .activity-row {
            display: flex;
            gap: 3px;
            margin-bottom: 3px;
        }

        .activity-cell {
            width: 12px;
            height: 12px;
            background-color: var(--bg-tertiary);
            border-radius: 2px;
            transition: transform 0.1s;
            cursor: pointer;
        }

        .activity-cell:hover {
            transform: scale(1.3);
        }

        .activity-cell.level-1 { background-color: #0e4429; }
        .activity-cell.level-2 { background-color: #006d32; }
        .activity-cell.level-3 { background-color: #26a641; }
        .activity-cell.level-4 { background-color: #39d353; }

        /* Toast Notification */
        .toast {
            position: fixed;
            bottom: 24px;
            left: 50%;
            transform: translateX(-50%) translateY(100px);
            background-color: var(--bg-secondary);
            border: 1px solid var(--border-color);
            padding: 12px 24px;
            border-radius: 8px;
            color: var(--text-primary);
            font-size: 14px;
            z-index: 300;
            transition: transform 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .toast.show {
            transform: translateX(-50%) translateY(0);
        }

        .toast i {
            color: var(--accent-green);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-wrap: wrap;
                gap: 16px;
            }

            .search-bar {
                order: 3;
                max-width: 100%;
                margin: 0;
            }

            .file-navigation {
                flex-direction: column;
                align-items: stretch;
            }

            .latest-commit {
                flex-wrap: wrap;
            }

            .file-commit {
                display: none;
            }

            .readme-content {
                padding: 16px;
            }
        }

        /* Skeleton Loading */
        .skeleton {
            background: linear-gradient(90deg, var(--bg-tertiary) 25%, var(--border-color) 50%, var(--bg-tertiary) 75%);
            background-size: 200% 100%;
            animation: loading 1.5s infinite;
            border-radius: 4px;
        }

        @keyframes loading {
            0% { background-position: 200% 0; }
            100% { background-position: -200% 0; }
        }

        /* Pulse Animation for Interactive Elements */
        .pulse {
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }

        /* Glow Effect */
        .glow-effect {
            box-shadow: 0 0 20px rgba(88, 166, 255, 0.3);
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="header">
        <div class="header-content">
            <a href="#" class="logo">
                <i class="fab fa-github"></i>
            </a>
            <div class="search-bar">
                <input type="text" placeholder="Type / to search">
            </div>
            <nav class="header-nav">
                <a href="#">Pull requests</a>
                <a href="#">Issues</a>
                <a href="#">Marketplace</a>
                <a href="#">Explore</a>
            </nav>
            <div class="header-nav">
                <button class="notification-btn">
                    <i class="far fa-bell"></i>
                </button>
                <button class="create-btn">
                    <i class="fas fa-plus"></i>
                    <i class="fas fa-caret-down"></i>
                </button>
                <img src="https://avatars.githubusercontent.com/u/583231?v=4" alt="User" class="avatar">
            </div>
        </div>
    </header>

    <!-- Main Container -->
    <main class="main-container">
        <!-- Repository Header -->
        <div class="repo-header">
            <div class="repo-title">
                <i class="fas fa-book-bookmark repo-icon"></i>
                <a href="#" class="repo-owner">octocat</a>
                <span class="repo-separator">/</span>
                <a href="#" class="repo-name">Hello-World</a>
                <span class="visibility-badge">Public</span>
            </div>
            <div class="repo-actions">
                <button class="action-btn" id="pinBtn" onclick="togglePin()">
                    <i class="far fa-bookmark"></i>
                    <span>Pin</span>
                </button>
                <button class="action-btn with-count" onclick="toggleWatch()">
                    <i class="far fa-eye"></i>
                    <span>Watch</span>
                    <i class="fas fa-caret-down dropdown-arrow"></i>
                </button>
                <span class="action-count" id="watchCount">187</span>
                
                <button class="action-btn with-count" onclick="toggleFork()">
                    <i class="fas fa-code-branch"></i>
                    <span>Fork</span>
                    <i class="fas fa-caret-down dropdown-arrow"></i>
                </button>
                <span class="action-count" id="forkCount">2.4k</span>
                
                <button class="action-btn with-count" id="starBtn" onclick="toggleStar()">
                    <i class="far fa-star"></i>
                    <span>Star</span>
                </button>
                <span class="action-count" id="starCount">2.5k</span>
            </div>
        </div>

        <!-- Tabs Navigation -->
        <nav class="tabs-nav">
            <a href="#" class="tab-item active">
                <i class="fas fa-code"></i>
                Code
            </a>
            <a href="#" class="tab-item">
                <i class="fas fa-circle-dot"></i>
                Issues
                <span class="tab-count">47</span>
            </a>
            <a href="#" class="tab-item">
                <i class="fas fa-code-pull-request"></i>
                Pull requests
                <span class="tab-count">12</span>
            </a>
            <a href="#" class="tab-item">
                <i class="fas fa-play"></i>
                Actions
            </a>
            <a href="#" class="tab-item">
                <i class="fas fa-table-columns"></i>
                Projects
            </a>
            <a href="#" class="tab-item">
                <i class="fas fa-book"></i>
                Wiki
            </a>
            <a href="#" class="tab-item">
                <i class="fas fa-shield-halved"></i>
                Security
            </a>
            <a href="#" class="tab-item">
                <i class="fas fa-chart-line"></i>
                Insights
            </a>
            <a href="#" class="tab-item">
                <i class="fas fa-gear"></i>
                Settings
            </a>
        </nav>

        <!-- Content Wrapper -->
        <div class="content-wrapper">
            <!-- Main Content -->
            <div class="main-content">
                <!-- File Navigation -->
                <div class="file-navigation">
                    <div class="branch-selector">
                        <button class="branch-btn" onclick="showBranchDropdown()">
                            <i class="fas fa-code-branch"></i>
                            <span>main</span>
                            <i class="fas fa-caret-down"></i>
                        </button>
                        <div class="branch-info">
                            <a href="#">
                                <i class="fas fa-code-branch"></i>
                                <strong>3</strong> branches
                            </a>
                            <a href="#">
                                <i class="fas fa-tag"></i>
                                <strong>12</strong> tags
                            </a>
                        </div>
                    </div>
                    <div class="code-actions">
                        <button class="add-file-btn">
                            <i class="fas fa-file-circle-plus"></i>
                            Add file
                            <i class="fas fa-caret-down"></i>
                        </button>
                        <button class="code-btn" onclick="showCodeDropdown()">
                            <i class="fas fa-code"></i>
                            Code
                            <i class="fas fa-caret-down"></i>
                        </button>
                    </div>
                </div>

                <!-- Latest Commit -->
                <div class="latest-commit">
                    <img src="https://avatars.githubusercontent.com/u/583231?v=4" alt="Commit author" class="commit-avatar">
                    <a href="#" class="commit-author">octocat</a>
                    <span class="commit-message">
                        <a href="#">Update README.md with new documentation</a>
                    </span>
                    <a href="#" class="commit-sha">e9f5d3a</a>
                    <span class="commit-time">2 days ago</span>
                    <div class="commit-count">
                        <i class="fas fa-clock-rotate-left"></i>
                        <a href="#"><strong>1,245</strong> commits</a>
                    </div>
                </div>

                <!-- File Explorer -->
                <div class="file-explorer" id="fileExplorer">
                    <!-- Files will be dynamically loaded -->
                </div>

                <!-- README Section -->
                <div class="readme-section">
                    <div class="readme-header">
                        <span class="readme-title">
                            <i class="fas fa-book"></i>
                            README.md
                        </span>
                        <div class="readme-actions">
                            <button class="readme-action-btn" title="Edit">
                                <i class="fas fa-pen"></i>
                            </button>
                            <button class="readme-action-btn" title="Copy">
                                <i class="far fa-copy"></i>
                            </button>
                            <button class="readme-action-btn" title="View raw">
                                <i class="fas fa-file-lines"></i>
                            </button>
                        </div>
                    </div>
                    <div class="readme-content">
                        <h1>Hello-World 👋</h1>
                        
                        <div class="badge-container">
                            <span class="badge badge-green">✓ Build Passing</span>
                            <span class="badge badge-blue">v2.1.0</span>
                            <span class="badge badge-purple">MIT License</span>
                        </div>

                        <p>
                            My first repository on GitHub! This is a demo repository to showcase 
                            the amazing features of GitHub and version control.
                        </p>

                        <h2>🚀 Features</h2>
                        <ul>
                            <li>Easy to use and understand</li>
                            <li>Great documentation</li>
                            <li>Active community support</li>
                            <li>Regular updates and maintenance</li>
                        </ul>

                        <h2>📦 Installation</h2>
                        <pre><code>git clone https://github.com/octocat/Hello-World.git
cd Hello-World
npm install</code></pre>

                        <h2>🛠️ Usage</h2>
                        <p>After installation, you can run the project using:</p>
                        <pre><code>npm start</code></pre>

                        <h2>🤝 Contributing</h2>
                        <p>
                            Contributions are always welcome! See <code>CONTRIBUTING.md</code> 
                            for ways to get started.
                        </p>

                        <h2>📝 License</h2>
                        <p>
                            This project is <a href="#">MIT</a> licensed.
                        </p>
                    </div>
                </div>
            </div>

            <!-- Sidebar -->
            <aside class="sidebar">
                <!-- About Section -->
                <div class="sidebar-section">
                    <div class="sidebar-header">
                        <span class="sidebar-title">About</span>
                        <button class="sidebar-action">
                            <i class="fas fa-gear"></i>
                        </button>
                    </div>
                    <p class="about-description">
                        My first repository on GitHub! This is a demo repository showcasing 
                        the basic features of GitHub.
                    </p>
                    <a href="https://hello-world.example.com" class="about-link">
                        <i class="fas fa-link"></i>
                        hello-world.example.com
                    </a>
                    <div class="topics">
                        <a href="#" class="topic-tag">hacktoberfest</a>
                        <a href="#" class="topic-tag">javascript</a>
                        <a href="#" class="topic-tag">documentation</a>
                        <a href="#" class="topic-tag">beginner-friendly</a>
                        <a href="#" class="topic-tag">demo</a>
                    </div>
                    <div class="about-meta">
                        <div class="meta-item">
                            <i class="far fa-file"></i>
                            <a href="#">MIT license</a>
                        </div>
                        <div class="meta-item">
                            <i class="fas fa-eye"></i>
                            <strong>187</strong> watching
                        </div>
                        <div class="meta-item">
                            <i class="fas fa-code-branch"></i>
                            <strong>2.4k</strong> forks
                        </div>
                        <div class="meta-item">
                            <i class="far fa-star"></i>
                            <strong>2.5k</strong> stars
                        </div>
                    </div>
                </div>

                <!-- Releases Section -->
                <div class="sidebar-section">
                    <div class="sidebar-header">
                        <span class="sidebar-title">Releases</span>
                        <a href="#" class="stat-item">4</a>
                    </div>
                    <div class="release-item">
                        <i class="fas fa-tag release-icon"></i>
                        <div class="release-info">
                            <h4>
                                <a href="#">v2.1.0</a>
                                <span class="release-tag">Latest</span>
                            </h4>
                            <span class="release-meta">Released 3 days ago</span>
                        </div>
                    </div>
                    <a href="#" class="stat-item" style="margin-top: 8px;">
                        + 3 releases
                    </a>
                </div>

                <!-- Packages Section -->
                <div class="sidebar-section">
                    <div class="sidebar-header">
                        <span class="sidebar-title">Packages</span>
                    </div>
                    <p style="color: var(--text-secondary); font-size: 14px;">
                        No packages published
                    </p>
                    <a href="#" class="stat-item" style="margin-top: 8px;">
                        Publish your first package
                    </a>
                </div>

                <!-- Contributors Section -->
                <div class="sidebar-section">
                    <div class="sidebar-header">
                        <span class="sidebar-title">Contributors</span>
                        <a href="#" class="stat-item">15</a>
                    </div>
                    <div class="contributors-grid" id="contributorsGrid">
                        <!-- Contributors will be loaded dynamically -->
                    </div>
                </div>

                <!-- Languages Section -->
                <div class="sidebar-section">
                    <div class="sidebar-header">
                        <span class="sidebar-title">Languages</span>
                    </div>
                    <div class="language-bar">
                        <div class="language-segment" style="width: 55%; background-color: #f1e05a;"></div>
                        <div class="language-segment" style="width: 25%; background-color: #563d7c;"></div>
                        <div class="language-segment" style="width: 15%; background-color: #e34c26;"></div>
                        <div class="language-segment" style="width: 5%; background-color: #3572A5;"></div>
                    </div>
                    <div class="language-list">
                        <div class="language-item">
                            <span class="language-dot" style="background-color: #f1e05a;"></span>
                            JavaScript 55.0%
                        </div>
                        <div class="language-item">
                            <span class="language-dot" style="background-color: #563d7c;"></span>
                            CSS 25.0%
                        </div>
                        <div class="language-item">
                            <span class="language-dot" style="background-color: #e34c26;"></span>
                            HTML 15.0%
                        </div>
                        <div class="language-item">
                            <span class="language-dot" style="background-color: #3572A5;"></span>
                            Python 5.0%
                        </div>
                    </div>
                </div>

                <!-- Activity Section -->
                <div class="sidebar-section">
                    <div class="sidebar-header">
                        <span class="sidebar-title">Activity</span>
                    </div>
                    <div class="activity-graph" id="activityGraph">
                        <!-- Activity graph will be generated dynamically -->
                    </div>
                </div>
            </aside>
        </div>
    </main>

    <!-- Code Dropdown Modal -->
    <div class="code-dropdown" id="codeDropdown" onclick="hideCodeDropdown(event)">
        <div class="code-dropdown-content" onclick="event.stopPropagation()">
            <div class="dropdown-header">
                <button class="dropdown-tab active" onclick="switchTab('local')">Local</button>
                <button class="dropdown-tab" onclick="switchTab('codespaces')">Codespaces</button>
            </div>
            <div class="dropdown-body" id="dropdownBody">
                <div class="clone-section">
                    <h4>
                        <i class="fas fa-lock"></i>
                        HTTPS
                    </h4>
                    <div class="clone-url">
                        <input type="text" value="https://github.com/octocat/Hello-World.git" readonly id="cloneUrl">
                        <button onclick="copyToClipboard()">
                            <i class="far fa-copy"></i>
                        </button>
                    </div>
                </div>
                <div class="clone-section">
                    <h4>
                        <i class="fas fa-key"></i>
                        SSH
                    </h4>
                    <div class="clone-url">
                        <input type="text" value="git@github.com:octocat/Hello-World.git" readonly>
                        <button onclick="copySSH()">
                            <i class="far fa-copy"></i>
                        </button>
                    </div>
                </div>
                <div class="dropdown-actions">
                    <a href="#" class="dropdown-action-btn">
                        <i class="fas fa-desktop"></i>
                        Open with GitHub Desktop
                    </a>
                    <a href="#" class="dropdown-action-btn">
                        <i class="fas fa-file-zipper"></i>
                        Download ZIP
                    </a>
                </div>
            </div>
        </div>
    </div>

    <!-- Toast Notification -->
    <div class="toast" id="toast">
        <i class="fas fa-check-circle"></i>
        <span id="toastMessage">Copied to clipboard!</span>
    </div>

    <script>
        // Sample data
        const files = [
            { type: 'folder', name: '.github', commit: 'Add GitHub templates', time: '3 months ago' },
            { type: 'folder', name: 'docs', commit: 'Update documentation structure', time: '2 weeks ago' },
            { type: 'folder', name: 'src', commit: 'Refactor main components', time: '5 days ago' },
            { type: 'folder', name: 'tests', commit: 'Add unit tests for core modules', time: '1 week ago' },
            { type: 'file', name: '.gitignore', commit: 'Update gitignore patterns', time: '2 months ago' },
            { type: 'file', name: 'CONTRIBUTING.md', commit: 'Add contribution guidelines', time: '1 month ago' },
            { type: 'file', name: 'LICENSE', commit: 'Add 
