# EH2 — Proxy Setting

**What is a Proxy?**

A proxy is a middle server between you and the internet. When you visit a website, instead of your real IP going to that site, the proxy IP goes. The website sees the proxy, not you.

Simple example — you send a letter but instead of your address, you write your friend's address. The receiver knows your friend, not you.

**Why Proxy is Important?**

It hides your real IP address. It protects your identity online. In ethical hacking, before testing any system, you hide yourself first. If you test without hiding, the target system logs your real IP. That is dangerous and unprofessional.

**Tools Used in Kali Linux

1. Anonsurf**

Anonsurf routes all your internet traffic through the Tor network. Every request you make goes through multiple servers around the world before reaching the target. Your real IP becomes completely hidden.

Start it — anonsurf start

Stop it — anonsurf stop

Check status — anonsurf status

**2. Kalitorify**

Same concept as Anonsurf. It forces all traffic through Tor. It works at the system level meaning every app on your Kali goes through Tor automatically. Good for full system anonymity.

**3. Whoami**

Whoami is an information gathering tool. It shows what information is visible about you on the internet right now. Your IP, location, ISP, DNS — everything that a target or anyone can see about you. Before starting any test, ethical hackers run whoami to check their anonymity level.
