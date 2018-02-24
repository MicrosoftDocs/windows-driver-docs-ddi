---
UID: NF:fltkernel.FltGetInstanceInformation
title: FltGetInstanceInformation function
author: windows-driver-content
description: The FltGetInstanceInformation routine returns information about a minifilter driver instance.
old-location: ifsk\fltgetinstanceinformation.htm
old-project: ifsk
ms.assetid: eb8ba04a-dbf8-4964-8b45-2620447418b5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltGetInstanceInformation, FltGetInstanceInformation routine [Installable File System Drivers], ifsk.fltgetinstanceinformation, fltkernel/FltGetInstanceInformation, FltApiRef_e_to_o_d476d1f7-fff3-45d1-91e9-25879ab9e90e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltGetInstanceInformation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetInstanceInformation function


## -description


The <b>FltGetInstanceInformation</b> routine returns information about a minifilter driver instance. 


## -syntax


````
NTSTATUS FltGetInstanceInformation(
  _In_  PFLT_INSTANCE              Instance,
  _In_  INSTANCE_INFORMATION_CLASS InformationClass,
  _Out_ PVOID                      Buffer,
  _In_  ULONG                      BufferSize,
  _Out_ PULONG                     BytesReturned
);
````


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. 


### -param InformationClass [in]

Type of information requested. This parameter can have one of the following values. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>InstanceBasicInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="..\fltuserstructures\ns-fltuserstructures-_instance_basic_information.md">INSTANCE_BASIC_INFORMATION</a> structure for the instance. 

</td>
</tr>
<tr>
<td>
<b>InstanceFullInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="..\fltuserstructures\ns-fltuserstructures-_instance_full_information.md">INSTANCE_FULL_INFORMATION</a> structure for the instance. 

</td>
</tr>
<tr>
<td>
<b>InstancePartialInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="..\fltuserstructures\ns-fltuserstructures-_instance_partial_information.md">INSTANCE_PARTIAL_INFORMATION</a> structure for the instance. 

</td>
</tr>
<tr>
<td>
<b>InstanceAggregateStandardInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives an <a href="..\fltuserstructures\ns-fltuserstructures-_instance_aggregate_standard_information.md">INSTANCE_AGGREGATE_STANDARD_INFORMATION</a> structure for the instance.  The <b>LegacyFilter</b> portion of the structure is not utilized. This structure is available starting with Windows Vista.

</td>
</tr>
</table>
 


### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the requested information. The type of the information returned in the buffer is defined by the <i>InformationClass</i> parameter. 


### -param BufferSize [in]

Size, in bytes, of the buffer that the <i>Buffer</i> parameter points to. The caller should set this parameter according to the given <i>InformationClass</i> value. 


### -param BytesReturned [out]

Pointer to a caller-allocated variable that receives the number of bytes returned in the buffer that <i>Buffer </i>points to. If the input value of <i>BufferSize</i> is too small, <b>FltGetInstanceInformation</b> returns STATUS_BUFFER_TOO_SMALL and sets this variable to the number of bytes required to store the requested information. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltGetInstanceInformation</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer that the <i>Buffer</i> parameter points to is not large enough to store the requested information. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for the <i>InformationClass</i> parameter.  For example, if <b>InstanceAggregateStandardInformation</b> is specified on the operating systems prior to Windows Vista, the routine will return STATUS_INVALID_PARAMETER.  This is an error code. 

</td>
</tr>
</table>
 




## -remarks



Given a pointer to a minifilter instance, this routine returns information about the minifilter instance.  The type of instance information returned is determined by the <i>InformationClass</i> parameter. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltgetfilterinformation.md">FltGetFilterInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltenumeratefilterinformation.md">FltEnumerateFilterInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltgetfilterinformation.md">FltGetFilterInformation</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_instance_full_information.md">INSTANCE_FULL_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolume.md">FltEnumerateInstanceInformationByVolume</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_instance_full_information.md">INSTANCE_FULL_INFORMATION</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_instance_basic_information.md">INSTANCE_BASIC_INFORMATION</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_instance_basic_information.md">INSTANCE_BASIC_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetInstanceInformation routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

