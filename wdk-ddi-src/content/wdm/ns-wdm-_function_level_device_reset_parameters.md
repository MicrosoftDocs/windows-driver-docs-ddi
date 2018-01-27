---
UID: NS:wdm._FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
title: _FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
author: windows-driver-content
description: The FUNCTION_LEVEL_DEVICE_RESET_PARAMETER structure is used as an argument to the DeviceReset routine of the GUID_DEVICE_RESET_INTERFACE_STANDARD interface.
old-location: kernel\function_level_device_reset_parameters.htm
old-project: kernel
ms.assetid: A9DDBE59-A318-427C-9BB4-ECB770C9B949
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.function_level_device_reset_parameters, wdm/FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, wdm/PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS structure pointer [Kernel-Mode Driver Architecture], _FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, *PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS structure [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: 
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Wdm.h
apiname: 
-	FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
product: Windows
targetos: Windows
req.typenames: FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, *PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS
req.product: Windows 10 or later.
---

# _FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS structure


## -description


The <b>FUNCTION_LEVEL_DEVICE_RESET_PARAMETER</b> structure  is used as an argument to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939354">DeviceReset</a> routine of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn928420">GUID_DEVICE_RESET_INTERFACE_STANDARD</a> interface. This structure specifies a callback routine that is called  when a function-level device reset is completed, and a context structure that is passed to the callback routine.


## -syntax


````
typedef struct _FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS {
  ULONG                    Size;
  PDEVICE_RESET_COMPLETION DeviceResetCompletion;
  PVOID                    CompletionContext;
} FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS, *PFUNCTION_LEVEL_DEVICE_RESET_PARAMETERS;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field DeviceResetCompletion

Pointer to a completion callback routine to be called when a function-level device reset is completed. The function prototype for this callback routine is defined as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
(*PDEVICE_RESET_COMPLETION)(
    _In_ NTSTATUS Status,
    _Inout_opt_ PVOID Context
    );</pre>
</td>
</tr>
</table></span></div>

### -field CompletionContext

Points to a caller-supplied context structure to be passed to the <i>DeviceResetCompletion</i> callback.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn928420">GUID_DEVICE_RESET_INTERFACE_STANDARD</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn939354">DeviceReset</a>

<a href="..\wdm\ns-wdm-_device_reset_interface_standard.md">DEVICE_RESET_INTERFACE_STANDARD</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FUNCTION_LEVEL_DEVICE_RESET_PARAMETERS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

