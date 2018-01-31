---
UID: NF:wdfworkitem.WDF_WORKITEM_CONFIG_INIT
title: WDF_WORKITEM_CONFIG_INIT function
author: windows-driver-content
description: The WDF_WORKITEM_CONFIG_INIT function initializes a driver's WDF_WORKITEM_CONFIG structure.
old-location: wdf\wdf_workitem_config_init.htm
old-project: wdf
ms.assetid: d24d9aea-0cdd-4130-9904-4e50c825612e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFWorkItemObjectRef_fa6a881e-6591-448a-9fc3-81ab60ff370c.xml, WDF_WORKITEM_CONFIG_INIT, kmdf.wdf_workitem_config_init, wdf.wdf_workitem_config_init, wdfworkitem/WDF_WORKITEM_CONFIG_INIT, WDF_WORKITEM_CONFIG_INIT function
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfworkitem.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
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
-	wdfworkitem.h
apiname:
-	WDF_WORKITEM_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: "*PWDF_WMI_PROVIDER_CONFIG, WDF_WMI_PROVIDER_CONFIG"
req.product: Windows 10 or later.
---

# WDF_WORKITEM_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_WORKITEM_CONFIG_INIT</b> function initializes a driver's <a href="..\wdfworkitem\ns-wdfworkitem-_wdf_workitem_config.md">WDF_WORKITEM_CONFIG</a> structure.


## -syntax


````
VOID WDF_WORKITEM_CONFIG_INIT(
  _Out_ PWDF_WORKITEM_CONFIG Config,
  _In_  PFN_WDF_WORKITEM     EvtWorkItemFunc
);
````


## -parameters




#### - Config [out]

A pointer to the caller-allocated <a href="..\wdfworkitem\ns-wdfworkitem-_wdf_workitem_config.md">WDF_WORKITEM_CONFIG</a> structure to initialize.


#### - EvtWorkItemFunc [in]

The address of the driver's <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> event callback function.


## -returns


None



## -remarks


Drivers must call <b>WDF_WORKITEM_CONFIG_INIT</b> before calling <a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemcreate.md">WdfWorkItemCreate</a>.

The <b>WDF_WORKITEM_CONFIG_INIT</b> function stores the pointer that the <i>EvtWorkItemFunc</i> parameter specifies and sets the <b>AutomaticSerialization</b> member of the <a href="..\wdfworkitem\ns-wdfworkitem-_wdf_workitem_config.md">WDF_WORKITEM_CONFIG</a> structure that is pointed to by the <i>Config</i> parameter to <b>TRUE</b>.



## -see-also

<a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a>

<a href="..\wdfworkitem\nf-wdfworkitem-wdfworkitemcreate.md">WdfWorkItemCreate</a>

<a href="..\wdfworkitem\ns-wdfworkitem-_wdf_workitem_config.md">WDF_WORKITEM_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_WORKITEM_CONFIG_INIT function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

