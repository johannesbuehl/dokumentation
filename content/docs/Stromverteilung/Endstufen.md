---
title: Endstufen
weight: 30
draft: false
math: true
---

Die Spannungsversorgung für die drei Crown XLS Endstufen der Lautsprecher in der Kirche, wie auch der Harmonic Design Aktivbass im Gemeindesaal werden durch den Lautsprecherconroller gesteuert.

## Logik

> [!IMPORTANT]
> Diese Logik ist geplant, aber noch nicht umgesetzt!
> Derzeit müssen die Endstufen durch die [Übersteuerung](#übersteuerung) ein- und ausgeschaltet werden.  
> Die Anlage im Gemeindesaal sind noch nicht angeschlossen.

Abhängig davon, ob die Ausgangszone _Kirche_ oder _Gemeindesaal_ aktiv ist, werden die beiden potentialfreien Relais-Ausgänge des AHM32 geschaltet. Diese

## Übersteuerung

Für den Fall, dass die unter [Logik](#logik) genannte Steuerung nicht funktionieren sollte, können die Endstufen und der Aktivbass durch Schalter in der Unterverteilung des Medienverteilers händisch angeschaltet werden.
Dies funktioniert komplett unabhängig vom Lautsprechercontroller.

Im Fehlerfall können somit die Endstufen dennoch angeschaltet und die Tonsignal an der Rückseite der Endstufen direkt aufgesteckt werden.

## Umsetzung

Der Lautsprechercontroller verfügt über 2 Relaisausgänge, deren Logik in der Software eingestellt werden können - hier schalten sie abhängig von den Zonen für die Kirche und den Gemeindesaal.

Zusätzlich stellt der AHM32 $\pu{12 V DC}$ bereit.
Diese schalten über die Relaisausgänge zwei Eltako Universalspannungsrelais, welche wiederum die 3 Endstufen beziehungsweise den Aktivbass mit Spannung versorgen.

Die Schalter für die Übersteuerung sind parallel zu den Eltako-Relais verbaut, sodass die Endstufen auch bei einem Komplettausfall des Lautsprechercontrollers eingeschaltet werden können.
