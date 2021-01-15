---
UID: NC:storport.HW_FIND_ADAPTER
title: HW_FIND_ADAPTER (storport.h)
description: The HwStorFindAdapter routine uses the supplied configuration to determine whether a specific HBA is supported and, if it is, to return configuration information about that adapter.
old-location: storage\hwstorfindadapter.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["HW_FIND_ADAPTER callback function"]
ms.keywords: HW_FIND_ADAPTER, HwStorFindAdapter, HwStorFindAdapter routine [Storage Devices], storage.hwstorfindadapter, stormini_844ef988-84c8-4f93-b732-eb0a2e8d611a.xml, storport/HwStorFindAdapter
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
req.irql: PASSIVE_LEVEL (See Remarks section.)
targetos: Windows
req.typenames: 
f1_keywords:
 - HW_FIND_ADAPTER
 - storport/HW_FIND_ADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Storport.h
api_name:
 - HW_FIND_ADAPTER
---

# HW_FIND_ADAPTER callback function


## -description

The **HwStorFindAdapter** routine uses the supplied configuration to determine whether a specific HBA is supported and, if it is, to return configuration information about that adapter.

## -parameters

### -param DeviceExtension

Supplies a per adapter storage area.

### -param HwContext 

[in]
Set to NULL.

### -param BusInformation 

[in]
Set to NULL.

### -param ArgumentString 

[in]
Supplies a **NULL**-terminated string with context information about the driver.

### -param ConfigInfo 

[in, out]
Supplies an initialized [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) structure that the miniport driver uses during initialization.

### -param Reserved3 

[in]
Reserved for system use.

## -returns

**HwStorFindAdapter** must return one of the following status values:

| Return code | Description |
| ----------- | ----------- |
| **SP_RETURN_FOUND** | Indicates that a supported HBA was found and that the HBA-relevant configuration information was successfully determined and set in the [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) structure. |
| **SP_RETURN_ERROR** | Indicates that an HBA was found but there was an error obtaining the configuration information. If possible, such an error should be logged with [**StorPortLogError**](nf-storport-storportlogerror.md). |
| **SP_RETURN_BAD_CONFIG** | Indicates that the supplied configuration information was invalid for the adapter. |
| **SP_RETURN_NOT_FOUND** | Indicates that no supported HBA was found for the supplied configuration information. |

## -remarks

Because the Storport driver supports only Plug and Play (PnP) devices, the *HwContext* and *BusInformation* parameters to **HwStorFindAdapter** are not supplied to non-virtual miniport drivers.

**HwStorFindAdapter** must set the **MaximumTransferLength** and **NumberOfPhysicalBreaks** fields in the *ConfigInfo* structure. Other than these fields, the [**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md) structure will always fully specify all adapter resources that are required to start the adapter.

The name **HwStorFindAdapter** is just a placeholder. The actual prototype of this routine is defined in *Storport.h* as follows:

```cpp
typedef
ULONG
HW_FIND_ADAPTER (
  _In_ PVOID  DeviceExtension,
  _In_ PVOID  HwContext,
  _In_ PVOID  BusInformation,
  _In_z_ PCHAR  ArgumentString,
  _Inout_ PPORT_CONFIGURATION_INFORMATION  ConfigInfo,
  _In_ PBOOLEAN  Reserved3
  );
```

In most cases StorPort calls the **HwStorFindAdapter** routine at IRQL == PASSIVE_LEVEL without acquiring any spin locks. The exception case is when the miniport does not support calling [**HwStorAdaptorControl**](nc-storport-hw_adapter_control.md) with the **ScsiRestartAdapter** control type. In this situation, StorPort will instead reinitialize the adapter by calling both  **HwStorFindAdapter** and [**HwStorInitialize**](nc-storport-hw_initialize.md). When this is the case, **HwStorFindAdapter** is called at IRQL == DISPATCH_LEVEL. Also, when in dump mode, **HwStorFindAdapter** is called at IRQL == HIGH_LEVEL.

### Examples

To define an **HwStorFindAdapter** callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps [Code Analysis for Drivers](/windows-hardware/drivers/devtest/code-analysis-for-drivers), [Static Driver Verifier](/windows-hardware/drivers/devtest/static-driver-verifier) (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a **HwStorFindAdapter** callback routine that is named *MyHwFindAdapter*, use the **HW_FIND_ADAPTER** type as shown in this code example:

```cpp
HW_FIND_ADAPTER MyHwFindAdapter;
```

Then, implement your callback routine as follows:

```cpp
_Use_decl_annotations_
ULONG
MyHwFindAdapter (
  _In_ PVOID  DeviceExtension,
  _In_ PVOID  HwContext,
  _In_ PVOID  BusInformation,
  _In_z_ PCHAR  ArgumentString,
  _Inout_ PPORT_CONFIGURATION_INFORMATION  ConfigInfo,
  _In_ PBOOLEAN  Reserved3
  );
  {
      ...
  }
```

The **HW_FIND_ADAPTER** function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the **HW_FIND_ADAPTER** function type in the header file are used. For more information about the requirements for function declarations, see [Declaring Functions Using Function Role Types for Storport Drivers](/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-storport-drivers). For information about _Use_decl_annotations_, see [Annotating Function Behavior](/cpp/code-quality/annotating-function-behavior?view=vs-2019).

## -see-also

[**HwStorInitialize**](nc-storport-hw_initialize.md)

[**PORT_CONFIGURATION_INFORMATION**](ns-storport-_port_configuration_information.md)

[**StorPortInitialize**](nf-storport-storportinitialize.md)

[**StorPortLogError**](nf-storport-storportlogerror.md)

