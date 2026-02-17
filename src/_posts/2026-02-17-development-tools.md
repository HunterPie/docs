---
layout: post
title: "Development Tools"
date: 2026-02-17 11:49 -0300
badge: docs
categories: [Documentation, Customization]
---

HunterPie includes development tools that help with development, debugging, and testing. These tools are hidden by default but can be enabled through feature flags.

## Enabling Development Tools

To access HunterPie's development features, you'll need to enable them through the feature flags system:

### Step 1: Enable Development Feature Flags

1. Open HunterPie Settings
2. Click on "Client" settings
3. Scroll all the way down to the bottom of the settings page
4. Enable **"Enable development feature flags"**

### Step 2: Reload Settings

1. **Exit** the settings page completely
2. **Re-enter** the settings page to reload all options

> This step is crucial as it refreshes the settings interface to show newly available options.
{: .prompt-info }

### Step 3: Access Feature Flags

1. In the settings page, scroll down on the sidebar
2. At the very bottom, you'll now see a **"Feature Flags"** option
3. Click on **"Feature Flags"**

### Step 4: Enable Advanced Development Features

1. In the Feature Flags section, find **"feature_enable_advanced_dev"**
2. **Enable** this feature flag

### Step 5: Restart HunterPie

1. Restart HunterPie by pressing <kbd>Ctrl</kbd>+<kbd>R</kbd>

After following these steps, you'll have access to HunterPie's full development options, including:

- **Mock Widgets** - Test themes with fake data without running the game
- **Overlay Manager** - Controls design mode, position and settings of the mocked widgets 

## Development Features

Once development tools are enabled, you can access various debugging and testing features that make theme development and troubleshooting much easier.

> **Important**: Some development features may impact performance and are intended for development use only. Disable them for normal gameplay.
{: .prompt-warning }
