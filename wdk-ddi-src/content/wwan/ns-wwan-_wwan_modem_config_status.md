---
UID: NS:wwan._WWAN_MODEM_CONFIG_STATUS
title: "_WWAN_MODEM_CONFIG_STATUS"
author: windows-driver-content
description: The WWAN_MODEM_CONFIG_STATUS structure represents a modem's configuration (config) status.
old-location: netvista\wwan_modem_config_status.htm
old-project: netvista
ms.assetid: 3A13CFBC-DBB4-4BB1-ABA4-AB145AED07AA
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WWAN_MODEM_CONFIG_STATUS, wwan/WWAN_MODEM_CONFIG_STATUS, netvista.wwan_modem_config_status, PWWAN_MODEM_CONFIG_STATUS, *PWWAN_MODEM_CONFIG_STATUS, wwan/PWWAN_MODEM_CONFIG_STATUS, WWAN_MODEM_CONFIG_STATUS structure [Network Drivers Starting with Windows Vista], PWWAN_MODEM_CONFIG_STATUS structure pointer [Network Drivers Starting with Windows Vista], _WWAN_MODEM_CONFIG_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	WWAN_MODEM_CONFIG_STATUS
product: Windows
targetos: Windows
req.typenames: "*PWWAN_MODEM_CONFIG_STATUS, WWAN_MODEM_CONFIG_STATUS"
req.product: Windows 10 or later.
---

# _WWAN_MODEM_CONFIG_STATUS structure


## -description


The <b>WWAN_MODEM_CONFIG_STATUS</b> structure represents a modem's configuration (config) status.


## -syntax


````
typedef struct _WWAN_MODEM_CONFIG_STATUS {
  WWAN_MODEM_CONFIG_STATE  ConfigState;
  WWAN_MODEM_CONFIG_REASON ConfigReason;
  ULONG                    PreviousConfigID;
  ULONG                    CurrentConfigID;
  DWORD                    DefaultOrNot;
} WWAN_MODEM_CONFIG_STATUS, *PWWAN_MODEM_CONFIG_STATUS;
````


## -struct-fields




### -field ConfigState

The modem's config state. For a list of defined values, see <a href="..\wwan\ne-wwan-_wwan_modem_config_state.md">WWAN_MODEM_CONFIG_STATE</a>.


### -field ConfigReason

The reason why the modem's config state change was triggered. For a list of defined values, see <a href="..\wwan\ne-wwan-_wwan_modem_config_reason.md">WWAN_MODEM_CONFIG_REASON</a>.


### -field PreviousConfigID

The previous config file's Config ID.


### -field CurrentConfigID

The current config file's Config ID.


### -field DefaultOrNot

Indicates if the default config file was selected, if available. 


## -remarks


Modem config files are identified using a Config ID, defined as a UUID whose value is determined by the IHV vendor. The value of each Config ID is unique and can be generated statically or dynamically. A Config ID of zero (00000000-0000-0000-000000000000) is a special case, meaning the Config ID is not available.

The config file's Config ID is reported to the OS during the config state change. When <b>ConfigState</b> is <i>Pending</i>, <b>PreviousConfigID</b> points to the previously activated modem config file or zero if there was no previously activated config file (such as during the device's first boot). The <b>CurrentConfigID</b> must always be set to zero when <b>ConfigState</b> is <i>Pending</i>.

When <b>ConfigState</b> is <i>Activated</i>, <b>PreviousConfigID</b> will be the same as in the <i>Pending</i> state but <b>CurrentConfigID</b> will point to a newly activated config file. In a case where no activation is required, <b>CurrentConfigID</b> will point to the existing <b>CurrentConfigID</b>.

If, during the modem config selection process, no match is found for existing custom config files, then a default config file is selected if available. The MBB driver indicates this by setting <b>DefaultOrNot</b> to TRUE. If no default config file exists, <b>CurrentConfigID</b> must be set to zero and <b>DefaultOrNot</b> must be set to FALSE. <b>DefaultOrNot</b> is only valid when <b>ConfigState</b> is <i>Activated</i>.

If the modem config selection process is triggered by SIM removal or no SIM, <b>CurrentConfigID</b> can be set either to 0 or <b>PreviousConfigID</b> in the <i>Activated</i> state. If the modem is removing the currently activated configuration, then <b>CurrentConfigID</b> will be set to zero. Otherwise, it will be set to the value of the previously activated configuration.

If the same config file is selected as the currently activated one, the MBB driver is not required to send a notification to the upper layer.



## -see-also

<a href="..\wwan\ns-wwan-_wwan_modem_config_info.md">WWAN_MODEM_CONFIG_INFO</a>

<a href="..\wwan\ne-wwan-_wwan_modem_config_state.md">WWAN_MODEM_CONFIG_STATE</a>

<a href="..\wwan\ne-wwan-_wwan_modem_config_reason.md">WWAN_MODEM_CONFIG_REASON</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_MODEM_CONFIG_STATUS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

