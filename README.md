# 🚀 NGINX Configuration Guide

A comprehensive guide covering NGINX server configuration, security hardening, performance optimization, caching strategies, load balancing, and CORS implementation.

---

## 📋 Table of Contents

- [Basic Server Configuration](#basic-server-configuration)
- [Application-Specific Configurations](#application-specific-configurations)
- [Proxy Configuration](#proxy-configuration)
- [Load Balancing](#load-balancing)
- [Rate Limiting & Connection Control](#rate-limiting--connection-control)
- [Compression (Gzip)](#compression-gzip)
- [Caching Strategies](#caching-strategies)
- [GeoIP-Based Routing](#geoip-based-routing)
- [Database Load Balancing](#database-load-balancing)
- [Security Configuration](#security-configuration)
- [CORS Configuration](#cors-configuration)
- [NGINX Variables Reference](#nginx-variables-reference)
- [Security Headers](#security-headers)
- [HTTP Response Codes](#http-response-codes)

---

## 🔧 Basic Server Configuration

### Simple Static Website

```nginx
server {
    listen 80;
    server_name domain;

    root /var/www/domain.com;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }

    error_log /var/log/nginx/domain_error_log;
    access_log /var/log/nginx/domain_access_log;
}
