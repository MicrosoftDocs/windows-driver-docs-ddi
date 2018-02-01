---
UID: NC:storport.VIRTUAL_HW_FIND_ADAPTER
title: VIRTUAL_HW_FIND_ADAPTER
author: windows-driver-content
description: The Storport virtual miniport uses configuration information supplied to the VirtualHwStorFindAdapter routine to further initialize itself.
old-location: storage\virtualhwstorfindadapter.htm
old-project: storage
ms.assetid: 55c16545-194e-4d23-b2e6-26821180eafa
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.virtualhwstorfindadapter, VirtualHwStorFindAdapter routine [Storage Devices], VirtualHwStorFindAdapter, VIRTUAL_HW_FIND_ADAPTER, VIRTUAL_HW_FIND_ADAPTER, storport/VirtualHwStorFindAdapter, storvmini_d41a0c2e-d224-4cfd-95e1-997b6a54904b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
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
-	UserDefined
apilocation:
-	Storport.h
apiname:
-	VirtualHwStorFindAdapter
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER"
req.product: Windows 10 or later.
---

# VIRTUAL_HW_FIND_ADAPTER callback


## -description


The Storport virtual miniport uses configuration information supplied to the <b>VirtualHwStorFindAdapter</b> routine to further initialize itself.


## -prototype


````
VIRTUAL_HW_FIND_ADAPTER VirtualHwStorFindAdapter;

ULONG VirtualHwStorFindAdapter(
   IN PVOID                               DeviceExtension,
   IN PVOID                               HwContext,
   IN PVOID                               BusInformation,
   IN PVOID                               LowerDevice,
   IN PCHAR                               ArgumentString,
   IN OUT PPORT_CONFIGURATION_INFORMATION ConfigInfo,
   OUT PBOOLEAN                           Again
)
{ ... }
````


## -parameters




### -param DeviceExtension

A pointer to the miniport driver's per-adapter non-paged storage area. The operating system-specific port driver allocates memory for and initializes this extension with zeros before it calls the miniport's <b>VirtualHwStorFindAdapter</b> routine.


### -param HwContext

A pointer to the PDO in the device stack. The HBA itself is the FDO. The PDO might belong to the Pci.sys driver if the miniport driver controls physical hardware. But in the case of a virtual miniport driver, the PDO belongs to the PnP manager.


### -param BusInformation

A pointer to the miniport's functional device object  (FDO).


### -param LowerDevice

A pointer to the device object controlled by the miniport's FDO.


### -param ArgumentString

A pointer to a null-terminated ASCII string. This string, if supplied, contains device information from the registry such as a base parameter.


### -param ConfigInfo

A pointer to a <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structure. The port driver initializes this structure with any known configuration information, such as values that the miniport driver's <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> set in the <a href="..\storport\ns-storport-_virtual_hw_initialization_data.md">VIRTUAL_HW_INITIALIZATION_DATA</a>. <b>VirtualHwStorFindAdapter</b>  must use any supplied information to determine if the virtual HBA it describes is one that the miniport driver supports. If so, <b>VirtualHwStorFindAdapter</b> initializes and configures that HBA and fills in any missing configuration information. If possible, a miniport driver should have default configuration values for each type of HBA that it supports, in the event that the operating system-dependent port driver cannot supply additional configuration information that was not provided by the miniport driver's <b>DriverEntry</b> routine.


### -param Again

Not used.


## -returns


<b>VirtualHwStorFindAdapter</b> must return one of the following status values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>SP_RETURN_FOUND</b></dt>
</dl>
</td>
<td width="60%">
Indicates that a supported HBA was found and that the HBA-relevant configuration information was determined successfully and set in the <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>SP_RETURN_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Indicates that an HBA was found, but an error occurred when it obtained the configuration information. If possible, such an error should be logged with <a href="..\srb\nf-srb-scsiportlogerror.md">ScsiPortLogError</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>SP_RETURN_BAD_CONFIG</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the supplied configuration information was invalid for the adapter.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>SP_RETURN_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
Indicates that no supported HBA was found for the supplied configuration information.

</td>
</tr>
</table> 



## -remarks


The <b>VirtualDevice</b> field in the configuration information structure must be set to <b>TRUE</b>. Other fields can be set as needed.

The port driver calls the Storport virtual miniport's <b>VirtualHwStorFindAdapter</b> at PASSIVE_LEVEL.

The name <b>VirtualHwStorFindAdapter</b> is placeholder text for the actual routine name. The actual prototype of this routine is defined in Srb.h as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
ULONG
VIRTUAL_HW_FIND_ADAPTER (
  _In_ PVOID  DeviceExtension,
  _In_ PVOID  HwContext,
  _In_ PVOID  BusInformation,
  _In_ PVOID  LowerDevice,
  _In_ PCHAR  ArgumentString,
  _Inout_ PPORT_CONFIGURATION_INFORMATION  ConfigInfo,
  _Out_ PBOOLEAN Again
  );</pre>
</td>
</tr>
</table></span></div>


## -see-also

<a href="..\storport\ns-storport-_virtual_hw_initialization_data.md">VIRTUAL_HW_INITIALIZATION_DATA</a>

<a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>

<a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a>

<a href="..\srb\nf-srb-scsiportlogerror.md">ScsiPortLogError</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20VirtualHwStorFindAdapter routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

