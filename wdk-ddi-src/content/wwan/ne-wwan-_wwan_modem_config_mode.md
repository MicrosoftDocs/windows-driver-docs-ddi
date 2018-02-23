---
UID: NE:wwan._WWAN_MODEM_CONFIG_MODE
title: "_WWAN_MODEM_CONFIG_MODE"
author: windows-driver-content
description: The WWAN_MODEM_CONFIG_MODE enumeration lists modem configuration modes.
old-location: netvista\wwan_modem_config_mode.htm
old-project: netvista
ms.assetid: 1AA3EDCC-EB6E-4118-8081-CA1914140683
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.wwan_modem_config_mode, wwan/WwanModemConfigModeModemCentric, WWAN_MODEM_CONFIG_MODE, wwan/WwanModemConfigModeMax, WwanModemConfigModeModemCentric, wwan/WwanModemConfigModeHostCentric, WwanModemConfigModeMax, *PWWAN_MODEM_CONFIG_MODE, WwanModemConfigModeHostCentric, wwan/PWWAN_MODEM_CONFIG_MODE, PWWAN_MODEM_CONFIG_MODE, wwan/WWAN_MODEM_CONFIG_MODE, wwan/WwanModemConfigModeUnknown, WWAN_MODEM_CONFIG_MODE enumeration [Network Drivers Starting with Windows Vista], PWWAN_MODEM_CONFIG_MODE enumeration pointer [Network Drivers Starting with Windows Vista], WwanModemConfigModeUnknown, _WWAN_MODEM_CONFIG_MODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_MODEM_CONFIG_MODE
product: Windows
targetos: Windows
req.typenames: WWAN_MODEM_CONFIG_MODE, *PWWAN_MODEM_CONFIG_MODE
req.product: Windows 10 or later.
---

# _WWAN_MODEM_CONFIG_MODE enumeration


## -description


The <b>WWAN_MODEM_CONFIG_MODE</b> enumeration lists modem configuration modes.


## -syntax


````
typedef enum _WWAN_MODEM_CONFIG_MODE { 
  WwanModemConfigModeUnknown       = 0,
  WwanModemConfigModeModemCentric,
  WwanModemConfigModeHostCentric,
  WwanModemConfigModeMax
} WWAN_MODEM_CONFIG_MODE, *PWWAN_MODEM_CONFIG_MODE;
````


## -enum-fields




### -field WwanModemConfigModeUnknown

The modem configuration mode is currently not available.


### -field WwanModemConfigModeModemCentric

The modem configuration mode is modem centric. The modem is responsible for the selection process of configuration based on UICC info or any other vendor-specified algorithm.


### -field WwanModemConfigModeHostCentric

The modem configuration mode is host centric. The host will inform the modem which configuration file the modem will use.


### -field WwanModemConfigModeMax

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks



The modem configuration mode shall not change during runtime. If a change is detected, it will be ignored by the OS.




## -see-also

<a href="..\wwan\ns-wwan-_wwan_modem_config_info.md">WWAN_MODEM_CONFIG_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_MODEM_CONFIG_MODE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

