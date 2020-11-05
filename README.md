Modro tipko lahko uporabimo za digitalni vhod interrupt (GPIO_EXT ...) in sicer je to pin PA0 (GPIO EXIT0).
Zelena LED lučka je na pinu PC9, modra LED lučka pa na pinu PC8.
Znotraj funkcije za klic callback funkcije uporabimo ukaz HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_9); za vklop/izklop zelene LED lučke.
Zapisana zakasnitev, ki jo proizvede zanka for znaša 2,8125 ms.
Ukaz HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_8); pa služi za utripanje modre LED lučke.
Za zakasnitev pa dodamo še ukaz HAL_Delay(500);
Kaj se zgodi, ko pritisnemo na modro tipko na STM32L1? Ko pritisnemo modro tipko se prižge/ufgasne zelena Led dioda. Modra led dioda pa še naprej utripa v frekvenci 1 Hz.
Ali pritisk na modro tipko vpliva na utripanje modre LED in zakaj? Pritisk na modro tipko ne vpliva na utripanje modre ledice, zaradi interrupta, ki smo ga nastavili tipki. 
KOMENTAR DELOVANJA: Z modro tipko prižgemo zeleno LED lučko, med tem ko modra LED lučka neprestano utripa s hrekvenco 1 Hz. S pritiskom na modro tipko pa ne vplivamo na utripanje modre LED lučke, to pa se pa zgodi zaradi interrupta, ki smo ga nastavili tipki. Zato ta program deluje dobro in brez zakasnitev.
