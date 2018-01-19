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
ms.keywords: _STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER
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
req.alt-api: VirtualHwStorFindAdapter
req.alt-loc: Storport.h
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
req.typenames: *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER
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
<dl>
<dt><b>SP_RETURN_FOUND</b></dt>
</dl>Indicates that a supported HBA was found and that the HBA-relevant configuration information was determined successfully and set in the <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structure.
<dl>
<dt><b>SP_RETURN_ERROR</b></dt>
</dl>Indicates that an HBA was found, but an error occurred when it obtained the configuration information. If possible, such an error should be logged with <a href="..\srb\nf-srb-scsiportlogerror.md">ScsiPortLogError</a>.
<dl>
<dt><b>SP_RETURN_BAD_CONFIG</b></dt>
</dl>Indicates that the supplied configuration information was invalid for the adapter.
<dl>
<dt><b>SP_RETURN_NOT_FOUND</b></dt>
</dl>Indicates that no supported HBA was found for the supplied configuration information.

 


## -remarks
The <b>VirtualDevice</b> field in the configuration information structure must be set to <b>TRUE</b>. Other fields can be set as needed.

The port driver calls the Storport virtual miniport's <b>VirtualHwStorFindAdapter</b> at PASSIVE_LEVEL.

The name <b>VirtualHwStorFindAdapter</b> is placeholder text for the actual routine name. The actual prototype of this routine is defined in Srb.h as follows:

To define an <b>VirtualHwStorFindAdapter</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>VirtualHwStorFindAdapter</b> callback routine that is named <i>MyVirtualHwFindAdapter</i>, use the <b>VIRTUAL_HW_FIND_ADAPTER</b> type as shown in this code example:

Then, implement your callback routine as follows:

The <b>VIRTUAL_HW_FIND_ADAPTER</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>VIRTUAL_HW_FIND_ADAPTER</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-us/library/jj159529.aspx">Annotating Function Behavior</a>.


## -see-also
<dl>
<dt>
<a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a>
</dt>
<dt>
<a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>
</dt>
<dt>
<a href="..\srb\nf-srb-scsiportlogerror.md">ScsiPortLogError</a>
</dt>
<dt>
<a href="..\storport\ns-storport-_virtual_hw_initialization_data.md">VIRTUAL_HW_INITIALIZATION_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20VirtualHwStorFindAdapter routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

