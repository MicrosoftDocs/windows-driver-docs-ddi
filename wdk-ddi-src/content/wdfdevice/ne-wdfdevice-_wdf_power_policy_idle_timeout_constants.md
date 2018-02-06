---
UID: NE:wdfdevice._WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS
title: "_WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS"
author: windows-driver-content
description: The WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS enumeration is reserved for internal use.
old-location: wdf\wdf_power_policy_idle_timeout_constants.htm
old-project: wdf
ms.assetid: a707c7b9-2fc9-48c8-9492-b911c126668b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS enumeration, wudfddi_types/WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS, IdleTimeoutDefaultConstant, wudfddi_types/IdleTimeoutDefaultConstant, wdfdevice/WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS, wdfdevice/IdleTimeoutDefaultConstant, _WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS, WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS, wdf.wdf_power_policy_idle_timeout_constants
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
-	wudfddi_types.h
apiname:
-	WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS
product: Windows
targetos: Windows
req.typenames: WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS
req.product: Windows 10 or later.
---

# _WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS</b> enumeration is reserved for internal use.


## -syntax


````
typedef enum _WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS { 
  IdleTimeoutDefaultConstant  = 0
} WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS;
````


## -enum-fields




### -field IdleTimeoutDefaultConstant

For internal use only.

