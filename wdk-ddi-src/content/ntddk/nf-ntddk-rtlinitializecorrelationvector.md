---
UID: NF:ntddk.RtlInitializeCorrelationVector
title: RtlInitializeCorrelationVector function
author: windows-driver-content
description: Initializes the specified correlation vector with the supplied GUID.
old-location: kernel\rtlinitializecorrelationvector.htm
old-project: kernel
ms.assetid: ebf5ccbe-3325-4d3d-86c9-230776f2c9ef
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/RtlInitializeCorrelationVector, kernel.rtlinitializecorrelationvector, RtlInitializeCorrelationVector function [Kernel-Mode Driver Architecture], RtlInitializeCorrelationVector
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.dll: NtosKrnl.exe (kernel mode)
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlInitializeCorrelationVector
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# RtlInitializeCorrelationVector function


## -description



			
              Initializes the specified correlation vector with
    the supplied GUID.


## -syntax


````
 NTSTATUS  RtlInitializeCorrelationVector(
  _Inout_ PCORRELATION_VECTOR CorrelationVector,
  _In_    int                 Version,
  _In_    const GUID          Guid
);
````


## -parameters




### -param CorrelationVector [in, out]

A pointer to a  <a href="..\ntddk\ns-ntddk-correlation_vector.md">CORRELATION_VECTOR</a> structure that represents the correlation vector to be initialized.


### -param Version [in]

The version of the correlation vector. Possible values are: 

<ul>
<li>RTL_CORRELATION_VECTOR_VERSION_1</li>
<li>RTL_CORRELATION_VECTOR_VERSION_2</li>
<li>RTL_CORRELATION_VECTOR_VERSION_CURRENT</li>
</ul>

### -param Guid [in]

The GUID to initialize the correlation vector. The first 22 bytes
            of the correlation vector are a base64 representation of the GUID. This value must not be NULL.


## -returns




Returns an NTSTATUS value that indicates the success of failure of the operation. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The correlation vector was successfully initialized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The supplied GUID is null.

</td>
</tr>
</table>
 




## -see-also

<a href="..\ntddk\ns-ntddk-correlation_vector.md">CORRELATION_VECTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlInitializeCorrelationVector function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

