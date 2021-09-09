---
UID: NC:storport.VIRTUAL_HW_FIND_ADAPTER
title: VIRTUAL_HW_FIND_ADAPTER (storport.h)
description: The Storport virtual miniport uses configuration information supplied to the VirtualHwStorFindAdapter routine to further initialize itself.
old-location: storage\virtualhwstorfindadapter.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["VIRTUAL_HW_FIND_ADAPTER callback function"]
ms.keywords: VIRTUAL_HW_FIND_ADAPTER, VirtualHwStorFindAdapter, VirtualHwStorFindAdapter routine [Storage Devices], storage.virtualhwstorfindadapter, storport/VirtualHwStorFindAdapter, storvmini_d41a0c2e-d224-4cfd-95e1-997b6a54904b.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VIRTUAL_HW_FIND_ADAPTER
 - storport/VIRTUAL_HW_FIND_ADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - VIRTUAL_HW_FIND_ADAPTER
---

# VIRTUAL_HW_FIND_ADAPTER callback function

## -description

The Storport virtual miniport uses configuration information supplied to the **VIRTUAL_HW_FIND_ADAPTER** routine to further initialize itself.

## -parameters

### -param DeviceExtension

A pointer to the miniport driver's per-adapter non-paged storage area. The operating system-specific port driver allocates memory for and initializes this extension with zeros before it calls the miniport's **VIRTUAL_HW_FIND_ADAPTER** routine.

### -param HwContext

A pointer to the PDO in the device stack. The HBA itself is the FDO. The PDO might belong to the Pci.sys driver if the miniport driver controls physical hardware. But in the case of a virtual miniport driver, the PDO belongs to the PnP manager.

### -param BusInformation

A pointer to the miniport's functional device object (FDO).

### -param LowerDevice

A pointer to the device object controlled by the miniport's FDO.

### -param ArgumentString

A pointer to a null-terminated ASCII string. This string, if supplied, contains device information from the registry such as a base parameter.

### -param ConfigInfo

A pointer to a [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) structure. The port driver initializes this structure with any known configuration information, such as values that the miniport driver's [DriverEntry](/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver) set in the [**VIRTUAL_HW_INITIALIZATION_DATA**](ns-storport-_virtual_hw_initialization_data.md). **VIRTUAL_HW_FIND_ADAPTER**  must use any supplied information to determine if the virtual HBA it describes is one that the miniport driver supports. If so, **VIRTUAL_HW_FIND_ADAPTER** initializes and configures that HBA and fills in any missing configuration information. If possible, a miniport driver should have default configuration values for each type of HBA that it supports, in the event that the operating system-dependent port driver cannot supply additional configuration information that was not provided by the miniport driver's **DriverEntry** routine.

### -param Again

Not used.

## -returns

**VIRTUAL_HW_FIND_ADAPTER** must return one of the following status values:

| Return code | Description |
| ----------- | ----------- |
| SP_RETURN_FOUND      | A supported HBA was found and that the HBA-relevant configuration information was determined successfully and set in the [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) structure. |
| SP_RETURN_ERROR      | An HBA was found, but an error occurred when it obtained the configuration information. If possible, such an error should be logged with [**ScsiPortLogError**](../srb/nf-srb-scsiportlogerror.md). |
| SP_RETURN_BAD_CONFIG | The supplied configuration information was invalid for the adapter. |
| SP_RETURN_NOT_FOUND  | No supported HBA was found for the supplied configuration information. |

## -remarks

The **VirtualDevice** field in the configuration information structure must be set to **TRUE**. Other fields can be set as needed.

The port driver calls the Storport virtual miniport's **VIRTUAL_HW_FIND_ADAPTER** at PASSIVE_LEVEL.

The name **VirtualHwStorFindAdapter** is placeholder text for the actual routine name. The actual prototype of this routine is defined in *Srb.h* as follows:

``` c
typedef
ULONG
VIRTUAL_HW_FIND_ADAPTER (
  _In_ PVOID  DeviceExtension,
  _In_ PVOID  HwContext,
  _In_ PVOID  BusInformation,
  _In_ PVOID  LowerDevice,
  _In_ PCHAR  ArgumentString,
  _Inout_ PPORT_CONFIGURATION_INFORMATION  ConfigInfo,
  _Out_ PBOOLEAN Again
  );
```

### Examples

To define a **VIRTUAL_HW_FIND_ADAPTER** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **VIRTUAL_HW_FIND_ADAPTER** callback routine that is named **MyVirtualHwFindAdapter**, use the **VIRTUAL_HW_FIND_ADAPTER** type as shown in this code example:

``` c
VIRTUAL_HW_FIND_ADAPTER MyVirtualHwFindAdapter;
```

Then, implement your callback routine as follows:

``` c
_Use_decl_annotations_
ULONG
MyVirtualHwFindAdapter (
  _In_ PVOID  DeviceExtension,
  _In_ PVOID  HwContext,
  _In_ PVOID  BusInformation,
  _In_ PVOID  LowerDevice,
  _In_ PCHAR  ArgumentString,
  _Inout_ PPORT_CONFIGURATION_INFORMATION  ConfigInfo,
  _Out_ PBOOLEAN Again
  );
  {
      ...
  }
```

The **VIRTUAL_HW_FIND_ADAPTER** function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **VIRTUAL_HW_FIND_ADAPTER** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](/visualstudio/code-quality/annotating-function-behavior).

## -see-also

[**HwStorFindAdapter**](nc-storport-hw_find_adapter.md)

[**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md)

[**ScsiPortLogError**](../srb/nf-srb-scsiportlogerror.md)

[**VIRTUAL_HW_INITIALIZATION_DATA**](ns-storport-_virtual_hw_initialization_data.md)
