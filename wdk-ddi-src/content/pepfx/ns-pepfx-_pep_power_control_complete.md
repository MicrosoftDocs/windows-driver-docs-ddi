---
UID: NS:pepfx._PEP_POWER_CONTROL_COMPLETE
title: "_PEP_POWER_CONTROL_COMPLETE"
author: windows-driver-content
description: The PEP_POWER_CONTROL_COMPLETE structure contains status information for a power control operation that the PEP previously requested and that the device driver has completed.
old-location: kernel\pep_power_control_complete.htm
old-project: kernel
ms.assetid: E270B609-2D47-4D55-94A6-BE82B2E5B77A
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PPEP_POWER_CONTROL_COMPLETE, PEP_POWER_CONTROL_COMPLETE, kernel.pep_power_control_complete, _PEP_POWER_CONTROL_COMPLETE, pepfx/PEP_POWER_CONTROL_COMPLETE, PEP_POWER_CONTROL_COMPLETE structure [Kernel-Mode Driver Architecture], pepfx/PPEP_POWER_CONTROL_COMPLETE, PPEP_POWER_CONTROL_COMPLETE structure pointer [Kernel-Mode Driver Architecture], *PPEP_POWER_CONTROL_COMPLETE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_POWER_CONTROL_COMPLETE
product: Windows
targetos: Windows
req.typenames: PEP_POWER_CONTROL_COMPLETE, *PPEP_POWER_CONTROL_COMPLETE
---

# _PEP_POWER_CONTROL_COMPLETE structure


## -description


The <b>PEP_POWER_CONTROL_COMPLETE</b> structure contains status information for a power control operation that the PEP previously requested and that the device driver has completed.


## -syntax


````
typedef struct _PEP_POWER_CONTROL_COMPLETE {
  PEPHANDLE DeviceHandle;
  LPCGUID   PowerControlCode;
  PVOID     RequestContext;
  SIZE_T    BytesReturned;
  NTSTATUS  Status;
} PEP_POWER_CONTROL_COMPLETE, *PPEP_POWER_CONTROL_COMPLETE;
````


## -struct-fields




### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field PowerControlCode

[in] A pointer to a <a href="http://msdn.microsoft.com/library/windows/desktop/aa373931(v=vs.85).aspx">GUID</a> value that specifies the power control operation that was performed. This is the same value that the PEP supplied in response to the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_WORK</a> notification to initiate the power control operation.


### -field RequestContext

[in] A pointer to the request context that was sent by the PEP in the <a href="..\pep_x\ns-pep_x-_pep_work_information.md">PEP_WORK_INFORMATION</a> structure that the PEP supplied in the original work request. Typically, this member points to a structure that contains a pointer to an output buffer to contain the results of the power control operation that was requested by the PEP.


### -field BytesReturned

[in] The size, in bytes, of the result data stored by the driver in the output buffer. For more information about this buffer, see the description of the <b>RequestContext</b> member.


### -field Status

[in] The status of the power control operation. If the operation was successful, the PEP sets this member to STATUS_SUCCESS. Otherwise, the PEP sets this member to an appropriate error status code.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186796">PEP_DPM_POWER_CONTROL_COMPLETE</a> notification. All five members of the structure contain input values that are supplied by

If the output buffer is too small to receive all of the result data from the operation, the PEP sets the <b>Status</b> member of the structure to STATUS_INSUFFICIENT_RESOURCES, sets  the <b>BytesReturned</b> member to the required size of the output buffer, and (typically) writes no data to the output buffer.




## -see-also

<a href="http://msdn.microsoft.com/library/windows/desktop/aa373931(v=vs.85).aspx">GUID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_POWER_CONTROL_COMPLETE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

