---
UID: NE:wwan._WWAN_UICC_PASSTHROUGH_ACTION
title: "_WWAN_UICC_PASSTHROUGH_ACTION"
author: windows-driver-content
description: The WWAN_UICC_PASSTHROUGH_ACTION enumeration defines the passthrough action specified by the MB host for a modem miniport adapter after it resets a UICC smart card.
old-location: netvista\wwan_uicc_passthrough_action.htm
old-project: netvista
ms.assetid: 4C9293CB-D92D-4C31-929F-16C1B8918933
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_UICC_PASSTHROUGH_ACTION, WWAN_UICC_PASSTHROUGH_ACTION, WWAN_UICC_PASSTHROUGH_ACTION enumeration [Network Drivers Starting with Windows Vista], WwanUiccPassThroughActionMaximum, WwanUiccPassThroughDisable, WwanUiccPassThroughEnable, _WWAN_UICC_PASSTHROUGH_ACTION, netvista.wwan_uicc_passthrough_action, wwan/WWAN_UICC_PASSTHROUGH_ACTION, wwan/WwanUiccPassThroughActionMaximum, wwan/WwanUiccPassThroughDisable, wwan/WwanUiccPassThroughEnable"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_UICC_PASSTHROUGH_ACTION
product: Windows
targetos: Windows
req.typenames: WWAN_UICC_PASSTHROUGH_ACTION, *PWWAN_UICC_PASSTHROUGH_ACTION
req.product: Windows 10 or later.
---

# _WWAN_UICC_PASSTHROUGH_ACTION enumeration


## -description


The <b>WWAN_UICC_PASSTHROUGH_ACTION</b> enumeration defines the passthrough action specified by the MB host for a modem miniport adapter after it resets a UICC smart card.


## -enum-fields




### -field WwanUiccPassThroughDisable

Indicates to disable passthrough to the UICC after reset. When UICC passthrough is disabled, the MB host treats the UICC as a regular Telecom UICC and expects a Telecom UICC file system to be present on the UICC.


### -field WwanUiccPassThroughEnable

Indicates to enable passthrough to the UICC after reset. When UICC passthrough is enabled, the modem miniport adapter treats the UICC as if it were in a passthrough mode that enables communication between the host and UICC, even if the UICC has no Telecom UICC file system. The miniport adapter does not send any APDUs to the card and does not interfere at any time with the communication between the host and the UICC.


### -field WwanUiccPassThroughActionMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-reset-operations">MB UICC reset operations</a>



<a href="https://msdn.microsoft.com/33711459-70C8-43D2-974D-B90EC0DD8ED6">WWAN_SET_UICC_RESET</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_UICC_PASSTHROUGH_ACTION enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
