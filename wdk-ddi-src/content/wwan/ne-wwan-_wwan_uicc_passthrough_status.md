---
UID: NE:wwan._WWAN_UICC_PASSTHROUGH_STATUS
title: _WWAN_UICC_PASSTHROUGH_STATUS (wwan.h)
description: The WWAN_UICC_PASSTHROUGH_STATUS enumeration defines the passthrough status of a modem miniport adapter for a UICC smart card.
old-location: netvista\wwan_uicc_passthrough_status.htm
tech.root: netvista
ms.assetid: 93D35A64-8394-41C2-BFB8-C8DE93619E75
ms.date: 05/02/2018
ms.keywords: "*PWWAN_UICC_PASSTHROUGH_STATUS, WWAN_UICC_PASSTHROUGH_STATUS, WWAN_UICC_PASSTHROUGH_STATUS enumeration [Network Drivers Starting with Windows Vista], WwanUiccPassThroughDisabled, WwanUiccPassThroughEnabled, WwanUiccPassThroughMaximum, _WWAN_UICC_PASSTHROUGH_STATUS, netvista.wwan_uicc_passthrough_status, wwan/WWAN_UICC_PASSTHROUGH_STATUS, wwan/WwanUiccPassThroughDisabled, wwan/WwanUiccPassThroughEnabled, wwan/WwanUiccPassThroughMaximum"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_UICC_PASSTHROUGH_STATUS
product:
- Windows
targetos: Windows
req.typenames: WWAN_UICC_PASSTHROUGH_STATUS, *PWWAN_UICC_PASSTHROUGH_STATUS
---

# _WWAN_UICC_PASSTHROUGH_STATUS enumeration


## -description


The <b>WWAN_UICC_PASSTHROUGH_STATUS</b> enumeration defines the passthrough status of a modem miniport adapter for a UICC smart card.


## -enum-fields




### -field WwanUiccPassThroughDisabled

Indicates that passthrough to the UICC is disabled. When UICC passthrough is disabled, the MB host treats the UICC as a regular Telecom UICC and expects a Telecom UICC file system to be present on the UICC.


### -field WwanUiccPassThroughEnabled

Indicates that passthrough to the UICC is enabled. When UICC passthrough is enabled, the modem miniport adapter treats the UICC as if it were in a passthrough mode that enables communication between the host and UICC, even if the UICC has no Telecom UICC file system. The miniport adapter does not send any APDUs to the card and does not interfere at any time with the communication between the host and the UICC.


### -field WwanUiccPassThroughStatusMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-uicc-reset-operations">MB UICC reset operations</a>



<a href="https://msdn.microsoft.com/1D53135F-3826-4546-A0AD-34697D186E8A">WWAN_UICC_RESET_INFO</a>
 

 

