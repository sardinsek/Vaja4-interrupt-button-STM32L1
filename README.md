# Vaja4-interrupt-button-STM32L1
Modro tipko lahko uporabima za digitalni vhod interrupt (GPIO_EXT…) in sicer je to pin PA0 (GPIO EXIT0).
Zelena LED je na pinu PC9, modra LED pa na pinu PC8.
Za vklop/izklop zelene LED uporabimo ukaz HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_9);.
Zakasnitev, ki jo proizvede zanka for pa znaša 2,8125 ms.
Za utripanje modre LED pa uporabimo ukaz HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_8);.
Ter v zanko za utripanje modre LED dodamo še ukaz za zakasnitev HAL_Delay(500);.
Kaj se zgodi, ko pritisnemo na modro tipko na STM32L1? Ko pritisnemo modro tipko se prižge/ugasne zelena LED. Modra led dioda pa še naprej utripa s frekvenco 1 Hz.
Ali pritisk na modro tipko vpliva na utripanje modre LED in zakaj? Pritisk na modro tipko ne vpliva na utripanje modre LED, zaradi interrupta, ki smo ga nastavili tipki. 
KOMENTAR DELOVANJA: Z modro tipko prižgemo zeleno LED lučko, med tem ko modra LED lučka neprestano utripa s frekvenco 1 Hz. S pritiskom na modro tipko ne vplivamo na utripanje modre LED lučke, to se pa zgodi zaradi interrupta, ki smo ga nastavili tipki. Zato ta program deluje dobro in brez zakasnitev.
