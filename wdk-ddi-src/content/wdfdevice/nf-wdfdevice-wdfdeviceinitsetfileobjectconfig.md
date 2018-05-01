---
UID: NF:wdfdevice.WdfDeviceInitSetFileObjectConfig
title: WdfDeviceInitSetFileObjectConfig function
author: windows-driver-content
description: The WdfDeviceInitSetFileObjectConfig method registers event callback functions and sets configuration information for the driver's framework file objects.
old-location: wdf\wdfdeviceinitsetfileobjectconfig.htm
old-project: wdf
ms.assetid: e309a741-1f61-4668-8176-baf0c8e26dff
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_97ec0f62-e8d2-46f9-b37a-13a632425a77.xml, WdfDeviceInitSetFileObjectConfig, WdfDeviceInitSetFileObjectConfig method, kmdf.wdfdeviceinitsetfileobjectconfig, wdf.wdfdeviceinitsetfileobjectconfig, wdfdevice/WdfDeviceInitSetFileObjectConfig
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: ChildDeviceInitAPI, ControlDeviceInitAPI, DeviceInitAPI, DriverCreate, FileObjectConfigured, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDeviceInitSetFileObjectConfig
product: Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceInitSetFileObjectConfig function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceInitSetFileObjectConfig</b> method registers event callback functions and sets configuration information for the driver's framework file objects.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param FileObjectConfig [in]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551319">WDF_FILEOBJECT_CONFIG</a> structure.


### -param FileObjectAttributes [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied object attributes for the driver's framework file objects. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


## -returns



None




## -remarks



If a driver calls <b>WdfDeviceInitSetFileObjectConfig</b>, it must do so before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.

By default, each framework file object inherits its synchronization scope and execution level from its parent device object. If the parent device object's synchronization scope and execution level are not <b>WdfSynchronizationScopeNone</b> and <b>WdfExecutionLevelPassive</b>, the driver must set the <b>WdfSynchronizationScopeNone</b> and <b>WdfExecutionLevelPassive</b> values in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that the <i>FileObjectAttributes </i>parameter specifies. Otherwise, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> will return an error status code. For more information about synchronization scope and execution level, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>.

For more information about calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about framework file objects, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>



#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure and a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551319">WDF_FILEOBJECT_CONFIG</a> structure and then calls <b>WdfDeviceInitSetFileObjectConfig</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES  attributes;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);
attributes.SynchronizationScope = WdfSynchronizationScopeNone;
WDF_FILEOBJECT_CONFIG_INIT(
                           &amp;deviceConfig,
                           MyEvtDeviceFileCreate,
                           MyEvtFileClose,
                           WDF_NO_EVENT_CALLBACK // No cleanup callback function
                           );
WdfDeviceInitSetFileObjectConfig(
                                 DeviceInit,
                                 &amp;deviceConfig,
                                 &amp;attributes
                                 );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551321">WDF_FILEOBJECT_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552402">WDF_OBJECT_ATTRIBUTES_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547268">WdfFdoInitSetEventCallbacks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548805">WdfPdoInitSetEventCallbacks</a>
 

 

