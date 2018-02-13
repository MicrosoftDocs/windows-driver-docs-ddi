---
UID: NF:fltkernel.FltEnumerateFilterInformation
title: FltEnumerateFilterInformation function
author: windows-driver-content
description: The FltEnumerateFilterInformation routine provides information about all the registered filter drivers (including minifilter and legacy filter drivers) in the system.
old-location: ifsk\fltenumeratefilterinformation.htm
old-project: ifsk
ms.assetid: c8bfa809-3f32-487c-991e-2ec040e3bc98
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: FltEnumerateFilterInformation, FltEnumerateFilterInformation routine [Installable File System Drivers], FltApiRef_e_to_o_dc4c496f-b21e-4b92-93c6-7efbe25400a6.xml, ifsk.fltenumeratefilterinformation, fltkernel/FltEnumerateFilterInformation
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
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltEnumerateFilterInformation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltEnumerateFilterInformation function


## -description


The <b>FltEnumerateFilterInformation</b> routine provides information about all the registered filter drivers (including minifilter and legacy filter drivers) in the system.


## -syntax


````
NTSTATUS FltEnumerateFilterInformation(
  _In_  ULONG                    Index,
  _In_  FILTER_INFORMATION_CLASS InformationClass,
  _Out_ PVOID                    Buffer,
  _In_  ULONG                    BufferSize,
  _Out_ PULONG                   BytesReturned
);
````


## -parameters




### -param Index [in]

Zero-based index of the filter driver for which the information is requested. This parameter identifies the filter in the global list of registered filter drivers. If the list contains <i>n</i> filter drivers, valid <i>Index</i> values range from 0 to <i>n</i>-1. If the <i>Index</i> value exceeds this range, <b>FltEnumerateFilterInformation</b> returns STATUS_NO_MORE_ENTRIES.


### -param InformationClass [in]

Type of information requested. This parameter can have one of the following values. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FilterFullInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives a <a href="..\fltuserstructures\ns-fltuserstructures-_filter_full_information.md">FILTER_FULL_INFORMATION</a> structure for the minifilter driver (legacy filter drivers are ignored).

</td>
</tr>
<tr>
<td>
<b>FilterAggregateBasicInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives a <a href="..\fltuserstructures\ns-fltuserstructures-_filter_aggregate_basic_information.md">FILTER_AGGREGATE_BASIC_INFORMATION</a> structure for the minifilter or legacy filter driver. This <i>InformationClass</i> value is available starting with Microsoft Windows Server 2003 SP1 and Windows XP SP2 with filter manager rollup.  For more about the filter manager rollup package for Windows XP SP2, see article 914882, "<a href="http://go.microsoft.com/fwlink/p/?linkid=3100&amp;ID=914882">The filter manager rollup package for Windows XP SP2</a>," in the Microsoft Knowledge Base.

</td>
</tr>
<tr>
<td>
<b>FilterAggregateStandardInformation</b>

</td>
<td>
The buffer pointed to by the <i>Buffer</i> parameter receives a <a href="..\fltuserstructures\ns-fltuserstructures-_filter_aggregate_standard_information.md">FILTER_AGGREGATE_STANDARD_INFORMATION</a> structure for the minifilter or legacy filter driver. This <i>InformationClass</i> value is available starting with Windows Vista.

</td>
</tr>
</table>
 


### -param Buffer [out]

Pointer to a caller-allocated buffer that receives the requested information. The type of the information returned in the buffer is defined by the <i>InformationClass</i> parameter. 


### -param BufferSize [in]

Size, in bytes, of the buffer that the <i>Buffer</i> parameter points to. The caller should set this parameter according to the given <i>InformationClass</i> value. 


### -param BytesReturned [out]

Pointer to a caller-allocated variable that receives the number of bytes returned in the buffer that <i>Buffer</i> points to. If the input value of <i>BufferSize</i> is too small, <b>FltEnumerateFilterInformation</b> returns STATUS_BUFFER_TOO_SMALL and sets this variable to the number of bytes required to store the requested information. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltEnumerateFilterInformation</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

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
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
A matching minifilter driver was found, but it is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for the <i>InformationClass</i> parameter. For example, if <b>FilterAggregateStandardInformation</b> is specified on operating systems prior to Windows Vista, the routine will return STATUS_INVALID_PARAMETER.  This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>
</td>
<td width="60%">
There are no more entries in the global list of registered filter drivers. (The value of the <i>Index</i> parameter is greater than or equal to the number of filter drivers.) This is a warning code. 

</td>
</tr>
</table>
 




## -remarks



Starting with Microsoft Windows Server 2003 SP1 and Windows XP SP2 with filter manager rollup, <b>FltEnumerateFilterInformation</b> provides information about file system filter drivers (also called "legacy filters") as well as minifilter drivers. On earlier versions of Windows, <b>FltEnumerateFilterInformation</b> only provides information about minifilter drivers.

The following pseudocode enumerates filter information for all registered filter drivers.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define InfoClass FilterAggregateStandardInformation   // Assumes Windows Vista or later operating system.

int i = 0;
while ( FltEnumerateFilterInformation(i, InfoClass, ...) != STATUS_NO_MORE_ENTRIES )
{
 Process acquired filter driver information returned by the Buffer parameter of FltEnumerateFilterInformation, if applicable.
 i++;
}</pre>
</td>
</tr>
</table></span></div>
<b>FltEnumerateFilterInformation</b> returns information about registered filter drivers, through the <i>Buffer</i> parameter, in order of decreasing distance from the underlying file system.  For example, assume that there are <i>n</i> filter drivers attached above an underlying file system.  Information about the filter driver attached farthest from the file system is returned first (with an <i>Index</i> parameter value of 0).  Information about the next-farthest attached filter driver is returned second (with an <i>Index</i> parameter value of 1), and so on.  Finally, information about the filter driver closest to the file system is returned last (with an <i>Index</i> parameter value of <i>n</i>-1).

<div class="alert"><b>Note</b>    Because filter drivers can register at any time, it is possible that two calls to <b>FltEnumerateFilterInformation</b> with the same <i>Index</i> might not return the same result. </div>
<div> </div>
To enumerate all registered minifilter drivers, call <a href="..\fltkernel\nf-fltkernel-fltenumeratefilters.md">FltEnumerateFilters</a>. 

To enumerate all registered legacy filter drivers, call <a href="..\ntifs\nf-ntifs-ioenumerateregisteredfilterslist.md">IoEnumerateRegisteredFiltersList</a>. 

To enumerate all instances of a given minifilter driver, call <a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyfilter.md">FltEnumerateInstanceInformationByFilter</a>. 

To enumerate all minifilter driver instances on a given volume, call <a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolume.md">FltEnumerateInstanceInformationByVolume</a>. 

To list volume information for all volumes that are known to the Filter Manager, call <a href="..\fltkernel\nf-fltkernel-fltenumeratevolumeinformation.md">FltEnumerateVolumeInformation</a>. 




## -see-also

<a href="..\fltuserstructures\ns-fltuserstructures-_filter_full_information.md">FILTER_FULL_INFORMATION</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_filter_aggregate_basic_information.md">FILTER_AGGREGATE_BASIC_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltenumeratefilters.md">FltEnumerateFilters</a>



<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyvolume.md">FltEnumerateInstanceInformationByVolume</a>



<a href="..\fltuserstructures\ns-fltuserstructures-_filter_aggregate_standard_information.md">FILTER_AGGREGATE_STANDARD_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltenumeratevolumeinformation.md">FltEnumerateVolumeInformation</a>



<a href="..\ntifs\nf-ntifs-ioenumerateregisteredfilterslist.md">IoEnumerateRegisteredFiltersList</a>



<a href="..\fltkernel\nf-fltkernel-fltenumerateinstanceinformationbyfilter.md">FltEnumerateInstanceInformationByFilter</a>



<a href="..\fltkernel\nf-fltkernel-fltgetfilterinformation.md">FltGetFilterInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltEnumerateFilterInformation routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

