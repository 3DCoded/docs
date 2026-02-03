---
title: Home
---

# About

I am a 3D printing enthusiast and the creator of the 3MS, DynamicMacros, and more.

[![Discord Shield](https://discord.com/api/guilds/1307104511663411210/widget.png?style=banner2&)](https://discord.gg/ekqxDhdGCg)

## Projects

<script>
    fetch('https://api.github.com/repos/3DCoded/3MS')
    .then(response => {
        if (response.ok) {
            return response.json();
        }
    }).then(data => {
        document.getElementById("3star").textContent = data.stargazers_count;
    })

    fetch('https://api.github.com/repos/3DCoded/DynamicMacros')
    .then(response => {
        if (response.ok) {
            return response.json();
        }
    }).then(data => {
        document.getElementById("dmacrostar").textContent = data.stargazers_count;
    })

    fetch('https://api.github.com/repos/3DCoded/KlipperMaintenance')
    .then(response => {
        if (response.ok) {
            return response.json();
        }
    }).then(data => {
        document.getElementById("kmaintainstar").textContent = data.stargazers_count;
    })
</script>

<div class="grid cards" markdown>

-   [![](3ms.png)](https://3ms.3dcoded.xyz) __3MS: Modular Multimaterial System for Klipper 3D printers__

    :octicons-star-16: <span id="3star">137</span>


    ---

    Simple multimaterial 3D printing on Klipper. No complex mechanism, just standard extruders synchronized to your printer. Plus, keep all the benefits of your existing extruder!

    [:octicons-arrow-right-24: Get Started](https://3ms.3dcoded.xyz)

- [![](dynamicmacros.png)]() __DynamicMacros: Never restart Klipper again for your simple macros__

    :octicons-star-16: <span id="dmacrostar">71</span>

    ---
    
    Quickly develop Klipper macros with ease. Save time without restarting Klipper. Use the extra features of DynamicMacros that make macros even more powerful!

    [:octicons-arrow-right-24: Get Started](https://dynamicmacros.3dcoded.xyz)

- [![](klippermaintenance.png)](https://3dcoded.xyz/KlipperMaintenance) __KlipperMaintenance: Keep your 3D printer running smoothly__

    :octicons-star-16: <span id="kmaintainstar">39</span>

    ---

    Easily schedule maintenance reminders in Klipper. Get reminded to maintain your 3D printer right in the Klipper console. Create as many custom maintenance reminders as you need!

    [:octicons-arrow-right-24: Get Started](https://3dcoded.xyz/KlipperMaintenance)

</div>

## Additional Projects

<div class="grid cards" markdown>

- __AllConfig: Easily view your configs as Klipper sees it__

    ---

    Easily diagnose configuration issues in Klipper without having to parse your `klippy.log`

    [:octicons-arrow-right-24: Get Started](https://github.com/3DCoded/Klipper-AllConfig)

</div>