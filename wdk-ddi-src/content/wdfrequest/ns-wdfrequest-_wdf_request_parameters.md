---
UID: NS:wdfrequest._WDF_REQUEST_PARAMETERS
title: _WDF_REQUEST_PARAMETERS
author: windows-driver-content
description: The WDF_REQUEST_PARAMETERS structure receives parameters that are associated with an I/O request.
old-location: wdf\wdf_request_parameters.htm
old-project: wdf
ms.assetid: 012e34c0-3cc6-49dc-94ad-d359d857720f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDF_REQUEST_PARAMETERS, WDF_REQUEST_PARAMETERS, *PWDF_REQUEST_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_REQUEST_PARAMETERS
req.alt-loc: wdfrequest.h
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
req.typenames: WDF_REQUEST_PARAMETERS, *PWDF_REQUEST_PARAMETERS
req.product: Windows 10 or later.
---

# _WDF_REQUEST_PARAMETERS structure



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_PARAMETERS</b> structure receives parameters that are associated with an I/O request.



## -syntax

````
typedef struct _WDF_REQUEST_PARAMETERS {
  USHORT           Size;
  UCHAR            MinorFunction;
  WDF_REQUEST_TYPE Type;
  union {
    struct {
      PIO_SECURITY_CONTEXT     SecurityContext;
      ULONG                    Options;
      USHORT POINTER_ALIGNMENT FileAttributes;
      USHORT                   ShareAccess;
      ULONG POINTER_ALIGNMENT  EaLength;
    } Create;
    struct {
      size_t                  Length;
      ULONG POINTER_ALIGNMENT Key;
      LONGLONG                DeviceOffset;
    } Read;
    struct {
      size_t                  Length;
      ULONG POINTER_ALIGNMENT Key;
      LONGLONG                DeviceOffset;
    } Write;
    struct {
      size_t                   OutputBufferLength;
      size_t POINTER_ALIGNMENT InputBufferLength;
      ULONG POINTER_ALIGNMENT  IoControlCode;
      PVOID                    Type3InputBuffer;
    } DeviceIoControl;
    struct {
      PVOID                   Arg1;
      PVOID                   Arg2;
      ULONG POINTER_ALIGNMENT IoControlCode;
      PVOID                   Arg4;
    } Others;
  } Parameters;
} WDF_REQUEST_PARAMETERS, *PWDF_REQUEST_PARAMETERS;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.


### -field MinorFunction

The IRP minor function code, if any, that is associated with the I/O request. Some major function codes have associated minor function codes.


### -field Type

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WDF_REQUEST_TYPE</a>-typed value that identifies the I/O request's type. 


### -field Parameters

Parameters that are unique for each IRP major function code. This member contains a subset of the Parameters member of the <a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a> structure. 



### -field Create

Parameters for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>.


### -field Read

Parameters for <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>.


### -field Write

Parameters for <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>.


### -field DeviceIoControl

Parameters for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>.


### -field Others

Use of this member is defined by the driver stack.

</dd>
</dl>

## -remarks
The <b>WDF_REQUEST_PARAMETERS</b> structure is used as input to <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>. Drivers must call <a href="..\wdfrequest\nf-wdfrequest-wdf_request_parameters_init.md">WDF_REQUEST_PARAMETERS_INIT</a> to initialize this structure before they call <b>WdfRequestGetParameters</b>.


## -see-also
<dl>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetparameters.md">WdfRequestGetParameters</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdf_request_parameters_init.md">WDF_REQUEST_PARAMETERS_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_REQUEST_PARAMETERS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

