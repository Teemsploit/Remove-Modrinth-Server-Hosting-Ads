// ==UserScript==
// @name         Remove Modrinth Server Hosting Ads
// @namespace    http://tampermonkey.net/
// @version      1.0
// @description  Removes server hosting referral ads from Modrinth (e.g., Medal links)
// @author       Teemsploit
// @match        https://modrinth.com/*
// @grant        none
// @run-at       document-idle
// ==/UserScript==

(function() {
    'use strict';

    function removeHostingAds() {
        const links = document.querySelectorAll('a[href^="/servers?plan"][class*="flex"]');
        links.forEach(link => {
            if (
                link.classList.contains("max-h-[250px]") &&
                link.classList.contains("min-h-[250px]") &&
                link.classList.contains("min-w-[300px]") &&
                link.classList.contains("max-w-[300px]")
            ) {
                link.remove();
            }
        });
    }

    removeHostingAds();

    const observer = new MutationObserver(removeHostingAds);
    observer.observe(document.body, { childList: true, subtree: true });
})();
