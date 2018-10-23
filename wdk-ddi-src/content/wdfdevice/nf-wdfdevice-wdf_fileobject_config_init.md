---
UID: NF:wdfdevice.WDF_FILEOBJECT_CONFIG_INIT
title: WDF_FILEOBJECT_CONFIG_INIT function
author: windows-driver-content
description: The WDF_FILEOBJECT_CONFIG_INIT function initializes a driver's WDF_FILEOBJECT_CONFIG structure.
old-location: wdf\wdf_fileobject_config_init.htm
tech.root: wdf
ms.assetid: 87ad817a-4a62-4061-949c-fe45bdfb44d5
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_ad75f4c0-79f7-42d6-8798-947cdcbfd8f1.xml, WDF_FILEOBJECT_CONFIG_INIT, WDF_FILEOBJECT_CONFIG_INIT function, kmdf.wdf_fileobject_config_init, wdf.wdf_fileobject_config_init, wdfdevice/WDF_FILEOBJECT_CONFIG_INIT
ms.topic: function
req.header: wdfdevice.h
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_FILEOBJECT_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_FILEOBJECT_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_FILEOBJECT_CONFIG_INIT</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551319">WDF_FILEOBJECT_CONFIG</a> structure.


## -parameters




### -param FileEventCallbacks [out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551319">WDF_FILEOBJECT_CONFIG</a> structure.


### -param EvtDeviceFileCreate [in, optional]

A pointer to the driver's <a href="https://msdn.microsoft.com/ee44c0bf-1fca-442d-8871-df6079e89ced">EvtDeviceFileCreate</a> event callback function.


### -param EvtFileClose [in, optional]

A pointer to the driver's <a href="https://msdn.microsoft.com/8ddcb9cb-d184-4ec8-a321-599394a8512e">EvtFileClose</a> event callback function.


### -param EvtFileCleanup [in, optional]

A pointer to the driver's <a href="https://msdn.microsoft.com/8ce3d316-3976-4af5-a0ae-af4e93f380a1">EvtFileCleanup</a> event callback function.


## -returns



None




## -remarks



The <b>WDF_FILEOBJECT_CONFIG_INIT</b> function sets the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff551319">WDF_FILEOBJECT_CONFIG</a> structure's <b>Size</b> member, stores the specified callback function pointers, sets the <b>FileObjectClass</b> member to <b>WdfFileObjectWdfCannotUseFsContexts</b>, and sets the <b>AutoForwardCleanupClose</b> member to <b>WdfUseDefault</b>. 


#### Examples

For a code example that uses <b>WDF_FILEOBJECT_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546107">WdfDeviceInitSetFileObjectConfig</a>.

<div class="code"></div>


