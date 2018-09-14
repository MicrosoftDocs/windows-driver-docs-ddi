---
UID: NF:wdfworkitem.WDF_WORKITEM_CONFIG_INIT
title: WDF_WORKITEM_CONFIG_INIT function
author: windows-driver-content
description: The WDF_WORKITEM_CONFIG_INIT function initializes a driver's WDF_WORKITEM_CONFIG structure.
old-location: wdf\wdf_workitem_config_init.htm
tech.root: wdf
ms.assetid: d24d9aea-0cdd-4130-9904-4e50c825612e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFWorkItemObjectRef_fa6a881e-6591-448a-9fc3-81ab60ff370c.xml, WDF_WORKITEM_CONFIG_INIT, WDF_WORKITEM_CONFIG_INIT function, kmdf.wdf_workitem_config_init, wdf.wdf_workitem_config_init, wdfworkitem/WDF_WORKITEM_CONFIG_INIT
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfworkitem.h
api_name:
-	WDF_WORKITEM_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_WORKITEM_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_WORKITEM_CONFIG_INIT</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff553086">WDF_WORKITEM_CONFIG</a> structure.


## -parameters




### -param Config [out]

A pointer to the caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff553086">WDF_WORKITEM_CONFIG</a> structure to initialize.


### -param EvtWorkItemFunc [in]

The address of the driver's <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> event callback function.


## -returns



None




## -remarks



Drivers must call <b>WDF_WORKITEM_CONFIG_INIT</b> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff551201">WdfWorkItemCreate</a>.

The <b>WDF_WORKITEM_CONFIG_INIT</b> function stores the pointer that the <i>EvtWorkItemFunc</i> parameter specifies and sets the <b>AutomaticSerialization</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553086">WDF_WORKITEM_CONFIG</a> structure that is pointed to by the <i>Config</i> parameter to <b>TRUE</b>.


#### Examples

For a code example that uses <b>WDF_WORKITEM_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551201">WdfWorkItemCreate</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553086">WDF_WORKITEM_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551201">WdfWorkItemCreate</a>
 

 

