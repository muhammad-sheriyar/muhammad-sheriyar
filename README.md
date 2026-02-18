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

        
