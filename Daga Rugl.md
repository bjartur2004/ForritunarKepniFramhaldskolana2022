## Daga Rugl
<details>
  
### Nafn: Daga Rugl

### Erfiðleiki : Erfitt?
  
### Lýsing : Nonni verslunarsjóri krónunar vill vita hvað það er lángt í hrekjavöku en hann er ekki það góður þegar það kemur að dagatölum þannig að hann bað þið um að skrifa kóða sem finnur það út fyirir sig

### Dæmi : Gerður kóða sem tekur inn dagsetningu `dagu, mánuður` og finnur síðan út hvað það er lángt í Hrekjavöku það er gert ráð fyirir því að það er ekki hlaupár

### Inntak : lína 1 : dagur (int) og lína 2 : mánudði (int)

### Úttak : fjödli daga til hrekjarvöku

### Dæmi Intak 1 :
```
4
9
```

### Dæmi Úttak 1 :
```
57
```

### Dæmi Intak 2 :
```
14
12
```

### Dæmi Úttak 1 :
```
321
```



Lausn með date time: 
```py
from datetime import date

dagur = int(input())
manudur = int(input())

ar = 2022 if manudur < 11 else 2021

day = date(ar, manudur, dagur)

holloweene = date(2022, 10, 31)


dagar = (holloweene - day).days

print(dagar)
```

Lausn án date time:
```py
dagur = int(input())
manudur = int(input())

# listi með hvað það eru margir dagar í mánuði þar sem indexið+1 af er númerið á mánuðinum
manada_dagar = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]

heildar_dagar = manada_dagar[manudur-1] - dagur

# ef að það þarf ekki að taka allt árið með
# sem sagt ef að það er ekki núþegar búinn hrekjavaka á þessu ári
if manudur < 11:
    for i in range(manudur,10):
            heildar_dagar += manada_dagar[i]
else:
    for i in range(manudur,12):
        heildar_dagar += manada_dagar[i]
    manudur = 0
    for i in range(manudur,10):
            heildar_dagar += manada_dagar[i]
            
print(heildar_dagar)
```
</details>
