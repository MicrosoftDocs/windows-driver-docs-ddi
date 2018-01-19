---
UID: NS:dispmprt._DXGK_TIMED_OPERATION_INTERFACE
title: _DXGK_TIMED_OPERATION_INTERFACE
author: windows-driver-content
description: The DXGK_TIMED_OPERATION_INTERFACE structure contains pointers to functions in the Timed Operation Interface, which is implemented by the display port driver.
old-location: display\dxgk_timed_operation_interface.htm
old-project: display
ms.assetid: 85b3764d-00b5-4e1d-bedc-c59a6b182735
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_TIMED_OPERATION_INTERFACE, *PDXGK_TIMED_OPERATION_INTERFACE, DXGK_TIMED_OPERATION_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_TIMED_OPERATION_INTERFACE
req.alt-loc: dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PDXGK_TIMED_OPERATION_INTERFACE, DXGK_TIMED_OPERATION_INTERFACE
---

# _DXGK_TIMED_OPERATION_INTERFACE structure



## -description
The DXGK_TIMED_OPERATION_INTERFACE structure contains pointers to functions in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570086">Timed Operation Interface</a>, which is implemented by the display port driver.



## -syntax

````
typedef struct _DXGK_TIMED_OPERATION_INTERFACE {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
  NTSTATUS               (*TimedOperationStart)(
      _Out_ DXGK_TIMED_OPERATION *Op, 
      _In_ const LARGE_INTEGER *Timeout, 
      _In_ BOOLEAN OsHandled);
  NTSTATUS               (*TimedOperationDelay)(
      _Inout_ DXGK_TIMED_OPERATION *Op, 
      _In_ KPROCESSOR_MODE WaitMode, 
      _In_ BOOLEAN Alertable, 
      _In_opt_ const LARGE_INTEGER *Interval);
  NTSTATUS               (*TimedOperationWaitForSingleObject)(
      _Inout_ DXGK_TIMED_OPERATION *Op, 
      _In_ PVOID Object, 
      _In_ KWAIT_REASON WaitReason, 
      _In_ KPROCESSOR_MODE WaitMode, 
      _In_ BOOLEAN Alertable, 
      _In_opt_ const LARGE_INTEGER *Timeout);
} DXGK_TIMED_OPERATION_INTERFACE, *PDXGK_TIMED_OPERATION_INTERFACE;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.


### -field Version

The version number of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570086">Timed Operation Interface</a>. Version number constants are defined in <i>Dispmprt.h</i> (for example, DXGK_TIMED_OPERATION_INTERFACE_VERSION_1).


### -field Context

A pointer to a context that is provided by the display port driver.


### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display port driver.


### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display port driver.


### -field TimedOperationStart

A pointer to the display port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff570084">TimedOperationStart</a> function. 


### -field Op

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff570084">TimedOperationStart</a> for more information.


### -field Timeout

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff570084">TimedOperationStart</a> for more information.


### -field OsHandled

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff570084">TimedOperationStart</a> for more information.

</dd>
</dl>

### -field TimedOperationDelay

A pointer to the display port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff570083">TimedOperationDelay</a> function. 


### -field Op

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff570083">TimedOperationDelay</a> for more information.


### -field WaitMode

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff570083">TimedOperationDelay</a> for more information.


### -field Alertable

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff570083">TimedOperationDelay</a> for more information.


### -field Interval

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff570083">TimedOperationDelay</a> for more information.

</dd>
</dl>

### -field TimedOperationWaitForSingleObject

A pointer to the display port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff570085">TimedOperationWaitForSingleObject</a> function. 


### -field Op

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff570085">TimedOperationWaitForSingleObject</a> for more information.


### -field Object

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff570085">TimedOperationWaitForSingleObject</a> for more information.


### -field WaitReason

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff570085">TimedOperationWaitForSingleObject</a> for more information.


### -field WaitMode

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff570085">TimedOperationWaitForSingleObject</a> for more information.


### -field Alertable

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff570085">TimedOperationWaitForSingleObject</a> for more information.


### -field Timeout

See <a href="https://msdn.microsoft.com/library/windows/hardware/ff570085">TimedOperationWaitForSingleObject</a> for more information.

</dd>
</dl>

## -remarks
The display miniport driver supplies the <b>Size</b> and <b>Version</b> members of this structure, and then calls <a href="..\dispmprt\nc-dispmprt-dxgkcb_query_services.md">DxgkCbQueryServices</a>, which fills in the remaining members of this structure.


## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkcb_query_services.md">DxgkCbQueryServices</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570086">Timed Operation Interface</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570083">TimedOperationDelay</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570084">TimedOperationStart</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570085">TimedOperationWaitForSingleObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_TIMED_OPERATION_INTERFACE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

