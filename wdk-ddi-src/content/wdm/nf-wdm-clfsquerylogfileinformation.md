---
UID: NF:wdm.ClfsQueryLogFileInformation
title: ClfsQueryLogFileInformation function (wdm.h)
description: The ClfsQueryLogFileInformation routine returns metadata and state information for a specified CLFS stream or its underlying physical log or both.
old-location: kernel\clfsquerylogfileinformation.htm
tech.root: kernel
ms.assetid: a907f219-9e4a-415f-821c-d419b7fde729
ms.date: 04/30/2018
ms.keywords: ClfsQueryLogFileInformation, ClfsQueryLogFileInformation routine [Kernel-Mode Driver Architecture], Clfs_ff89b511-dc33-4407-b967-170b82cb70c3.xml, kernel.clfsquerylogfileinformation, wdm/ClfsQueryLogFileInformation
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Clfs.sys
- Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
- ClfsQueryLogFileInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# ClfsQueryLogFileInformation function


## -description


The <b>ClfsQueryLogFileInformation</b> routine returns metadata and state information for a specified CLFS stream or its underlying physical log or both.


## -parameters




### -param plfoLog [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_file_object">LOG_FILE_OBJECT</a> structure that represents a CLFS stream. The caller previously obtained this pointer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfscreatelogfile">ClfsCreateLogFile</a>.


### -param eInformationClass [in]

A value from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_cls_log_information_class">CLFS_LOG_INFORMATION_CLASS</a> enumeration that specifies the type of information being requested.


### -param pinfoInputBuffer

Optional input buffer which is required for some information classes.


### -param cbinfoInputBuffer

Length in bytes of pinfoInputBuffer.


### -param pinfoBuffer [out]

A pointer to a buffer that receives the log information. The structure of this buffer depends on the value of <i>eInformationClass</i>. The following table shows the relationship between the information class and the data type of the buffer.

<table>
<tr>
<th>Value of <i>eInformationClass</i></th>
<th>Type of buffer pointed to by <i>pinfoBuffer</i></th>
</tr>
<tr>
<td>
<b>ClfsLogBasicInformation</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_cls_information">CLFS_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogBasicInformationPhysical</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_cls_information">CLFS_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogNameInformation</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_clfs_log_name_information">CLFS_LOG_NAME_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogPhysicalNameInformation</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_clfs_log_name_information">CLFS_LOG_NAME_INFORMATION</a>


</td>
</tr>
<tr>
<td>
<b>ClfsLogStreamIdentifierInformation</b>

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_clfs_stream_id_information">CLFS_STREAM_ID_INFORMATION</a>


</td>
</tr>
</table>
 


### -param pcbInfoBuffer

Length in bytes of the incoming information buffer.




#### - pcbBuffer [in, out]

The size, in bytes, of the buffer pointed to by <i>pinfoBuffer</i>.


## -returns



<b>ClfsQueryLogFileInformation</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



For an explanation of CLFS concepts and terminology, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-common-log-file-system">Common Log File System</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-clfssetlogfileinformation">ClfsSetLogFileInformation</a>
 

 

