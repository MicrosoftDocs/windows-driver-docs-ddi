---
UID: NF:wudfinterrupt.WDF_INTERRUPT_EXTENDED_POLICY_INIT
title: WDF_INTERRUPT_EXTENDED_POLICY_INIT function
author: windows-driver-content
description: The WDF_INTERRUPT_EXTENDED_POLICY_INIT function initializes a WDF_INTERRUPT_EXTENDED_POLICY structure.
old-location: wdf\wdf_interrupt_extended_policy_init_umdf.htm
old-project: wdf
ms.assetid: 6CD02F5B-0E34-46F5-8AEA-3B30293E1875
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_INTERRUPT_EXTENDED_POLICY_INIT function, wudfinterrupt/WDF_INTERRUPT_EXTENDED_POLICY_INIT, umdf.wdf_interrupt_extended_policy_init, wdf.wdf_interrupt_extended_policy_init_umdf, WDF_INTERRUPT_EXTENDED_POLICY_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfinterrupt.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfinterrupt.h
apiname:
-	WDF_INTERRUPT_EXTENDED_POLICY_INIT
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_PRIORITY, *PWDF_INTERRUPT_PRIORITY
req.product: Windows 10 or later.
---

# WDF_INTERRUPT_EXTENDED_POLICY_INIT function


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


      The <a href="..\wudfinterrupt\nf-wudfinterrupt-wdf_interrupt_extended_policy_init.md">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a> function initializes a <a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_extended_policy.md">WDF_INTERRUPT_EXTENDED_POLICY</a> structure.


## -syntax


````
VOID WDF_INTERRUPT_EXTENDED_POLICY_INIT(
  _Out_ PWDF_INTERRUPT_EXTENDED_POLICY PolicyAndGroup
);
````


## -parameters




### -param ExtendedPolicy

TBD



#### - PolicyAndGroup [out]

A pointer to a driver-allocated <a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_extended_policy.md">WDF_INTERRUPT_EXTENDED_POLICY</a> structure.


## -returns


None



## -remarks


The <a href="..\wudfinterrupt\nf-wudfinterrupt-wdf_interrupt_extended_policy_init.md">WDF_INTERRUPT_EXTENDED_POLICY_INIT</a> function zeros the specified <a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_extended_policy.md">WDF_INTERRUPT_EXTENDED_POLICY</a> structure and sets the structure's <b>Size</b> member. It also sets the structure's <b>Policy</b> member to <b>WdfIrqPolicyMachineDefault</b> and sets the structure's <b>Priority</b> member to <b>WdfIrqPriorityUndefined</b>.



## -see-also

<a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_extended_policy.md">WDF_INTERRUPT_EXTENDED_POLICY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_INTERRUPT_EXTENDED_POLICY_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

