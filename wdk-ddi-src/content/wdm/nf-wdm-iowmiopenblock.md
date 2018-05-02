---
UID: NF:wdm.IoWMIOpenBlock
title: IoWMIOpenBlock function
author: windows-driver-content
description: The IoWMIOpenBlock routine opens the WMI data block object for the specified WMI class.
old-location: kernel\iowmiopenblock.htm
old-project: kernel
ms.assetid: c23d1861-59df-4bd4-a005-173ccac53049
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IoWMIOpenBlock, IoWMIOpenBlock routine [Kernel-Mode Driver Architecture], k104_19f378c4-3729-4668-aef0-0e675d2e1ae4.xml, kernel.iowmiopenblock, wdm/IoWMIOpenBlock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Ntddk.h, Ntifs.h. The WMIGUID_XXX values are declared in Wmistr.h. To use them, include Wmistr.h.
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating system.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoWMIOpenBlock
product: Windows
targetos: Windows
req.typenames: 
---

# IoWMIOpenBlock function


## -description


The <b>IoWMIOpenBlock</b> routine opens the WMI data block object for the specified WMI class.


## -parameters




### -param Guid

TBD


### -param DesiredAccess [in]

Specifies the desired access rights to the data block object. The caller must have particular access rights to perform certain operations. 

The following is a description of each access right bit and the operations it allows:





#### WMIGUID_EXECUTE

The data block object can be used to run WMI class methods. This flag must be set to use <a href="https://msdn.microsoft.com/library/windows/hardware/ff550438">IoWMIExecuteMethod</a> on the data block object. 



#### WMIGUID_NOTIFICATION

The data block object can be used to register event notification callbacks. This flag must be set to use <a href="https://msdn.microsoft.com/library/windows/hardware/ff550484">IoWMISetNotificationCallback</a>, and can only be used for WMI event blocks. Callers that specify this flag must also specify the SYNCHRONIZE flag.



#### WMIGUID_QUERY

The data block object can be used to query WMI class properties. This flag must be set to use any of the <b>IoWMIQuery<i>Xxx</i></b> routines on the data block object. 



#### WMIGUID_SET

The data block object can be used to set WMI class properties. This flag must be set to use any of the <b>IoWMISet<i>Xxx</i></b> routines on the data block object. 


### -param DataBlockObject [out]

Pointer to a memory location where the routine returns a pointer to the data block object.


#### - DataBlockGuid [in]

Specifies the GUID for WMI class.


## -returns



Returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.




## -remarks



The caller uses <b>IoWMIOpenBlock</b> to create a data block object for the specified WMI class GUID. Subsequently, the caller can use the data block object to read or write WMI class properties, run WMI class methods, and register callbacks for WMI events.

Use the <b>IoWMIQuery<i>Xxx</i></b> and <b>IoWMISet<i>Xxx</i></b> routines to read and write WMI class properties. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff550438">IoWMIExecuteMethod</a> to run WMI class methods, and use <a href="https://msdn.microsoft.com/library/windows/hardware/ff550484">IoWMISetNotificationCallback</a> to register a WMI event notification callback.

Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a> to close the data block object once it is no longer needed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550438">IoWMIExecuteMethod</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550463">IoWMIQueryAllData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550467">IoWMIQueryAllDataMultiple</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550471">IoWMIQuerySingleInstance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550477">IoWMIQuerySingleInstanceMultiple</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550484">IoWMISetNotificationCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550493">IoWMISetSingleInstance</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550495">IoWMISetSingleItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>
 

 

