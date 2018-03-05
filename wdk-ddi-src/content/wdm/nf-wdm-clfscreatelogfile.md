---
UID: NF:wdm.ClfsCreateLogFile
title: ClfsCreateLogFile function
author: windows-driver-content
description: The ClfsCreateLogFile routine creates or opens a CLFS stream. If necessary, ClfsCreateLogFile also creates the underlying physical log that holds the stream's records.
old-location: kernel\clfscreatelogfile.htm
old-project: kernel
ms.assetid: 297f7b03-efd0-4e9c-a758-1a3b5b89511d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ClfsCreateLogFile, ClfsCreateLogFile routine [Kernel-Mode Driver Architecture], Clfs_79aa05cc-fff5-404a-93c6-89c9d938f104.xml, kernel.clfscreatelogfile, wdm/ClfsCreateLogFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsCreateLogFile
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ClfsCreateLogFile function


## -description


The <b>ClfsCreateLogFile</b> routine creates or opens a CLFS stream. If necessary, <b>ClfsCreateLogFile</b> also creates the underlying physical log that holds the stream's records.


## -syntax


````
NTSTATUS ClfsCreateLogFile(
  _Out_    PPLOG_FILE_OBJECT    pplfoLog,
  _In_     PUNICODE_STRING      puszLogFileName,
  _In_     ACCESS_MASK          fDesiredAccess,
  _In_     ULONG                dwShareMode,
  _In_opt_ PSECURITY_DESCRIPTOR psdLogFile,
  _In_     ULONG                fCreateDisposition,
  _In_     ULONG                fCreateOptions,
  _In_     ULONG                fFlagsAndAttributes,
  _In_     ULONG                fLogOptionFlag,
  _In_opt_ PVOID                pvContext,
  _In_     ULONG                cbContext
);
````


## -parameters




### -param pplfoLog [out]

A pointer to a variable that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents an open instance of the stream.


### -param puszLogFileName [in]

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that supplies the name of the stream or the underlying physical log. 

If the stream already exists and is the only stream of a dedicated log, the name has the form log:<i>physical log name</i>, where <i>physical log name</i> is the path name, on the underlying file system, of the existing physical log that contains the stream's records.

If the stream does not already exist and is to become the only stream of a dedicated log (that does not yet exist), the name has the form log:<i>physical log name</i>, where <i>physical log name</i> is the path name, on the underlying file system, of the physical log that will be created to hold the stream's records.

If the stream is (or is to become) one of the streams of a multiplexed log, the name has the form log:<i>physical log name</i>::<i>stream name</i>, where <i>physical log name</i> is the path name, on the underlying file system, of the physical log that holds the stream's records, and <i>stream name</i> is the name of a stream that shares (or will share) that physical log.

If you want to create a multiplexed log that has no streams for the moment, use a name of the form log:<i>physical log name</i>::, where <i>physical log name</i> is the path name, on the underlying file system, of the physical log to be created.

The following list gives some examples of valid names.

<ul>
<li>
"Log:c:\myLog" creates or opens a dedicated log and its one stream.

</li>
<li>
"Log:c:\myCommonLog::" creates a multiplexed log that does not yet have any streams.

</li>
<li>
"Log:c:\myCommonLog::Stream1" creates or opens one of the streams (Stream1) of a multiplexed log.

</li>
</ul>

### -param fDesiredAccess [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> that supplies the type of access the client will have (by using the pointer returned in <i>pplfoLog</i>) to the stream. If this parameter is zero, clients can query the stream for its attributes, but cannot read from or write to the stream. This parameter can be zero or any combination of the following flags:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
GENERIC_READ

</td>
<td>
The client has read access to the stream.

</td>
</tr>
<tr>
<td>
GENERIC_WRITE

</td>
<td>
The client has write access to the stream.

</td>
</tr>
<tr>
<td>
DELETE

</td>
<td>
The client can mark the stream for deletion.

</td>
</tr>
</table>
 


### -param dwShareMode [in]

The sharing mode of the stream, which can be zero (not shared) or any combination of the following flags:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_SHARE_DELETE

</td>
<td>
Subsequent requests to open the stream with delete access will succeed.

</td>
</tr>
<tr>
<td>
FILE_SHARE_READ

</td>
<td>
Subsequent requests to open the stream with read access will succeed.

</td>
</tr>
<tr>
<td>
FILE_SHARE_WRITE

</td>
<td>
Subsequent requests to open the stream with write access will succeed.

</td>
</tr>
</table>
 


### -param psdLogFile [in, optional]

A pointer to a <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> structure that supplies security attributes for the stream. This parameter can be <b>NULL</b>. 


### -param fCreateDisposition [in]

The action to take that depends on whether the stream already exists. This parameter must be set to one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
CREATE_NEW

</td>
<td>
Create a new stream if the stream does not already exits. Fail if the stream already exists.

</td>
</tr>
<tr>
<td>
OPEN_EXISTING

</td>
<td>
Open an existing stream. Fail if the stream does not already exist.

</td>
</tr>
<tr>
<td>
OPEN_ALWAYS

</td>
<td>
Open an existing stream. Create the stream if it does not already exist.

</td>
</tr>
</table>
 


### -param fCreateOptions [in]

A set of flags that specify options to apply when creating or opening the stream. This parameter can be zero or a compatible combination of the following flags:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_NO_INTERMEDIATE_BUFFERING

</td>
<td>
The stream's records cannot be cached in a driver's internal buffers.

</td>
</tr>
<tr>
<td>
FILE_SYNCHRONOUS_IO_ALERT

</td>
<td>
All operations on the stream are performed synchronously. Any wait on behalf of the caller is subject to premature termination from alerts. If this flag is set, the FILE_SYNCHRONOUS_IO_NONALERT flag must be cleared.

</td>
</tr>
<tr>
<td>
FILE_SYNCHRONOUS_IO_NONALERT

</td>
<td>
All operations on the stream are performed synchronously. Waits in the system that synchronize I/O queuing and completion are not subject to alerts. If this flag is set, the FILE_SYNCHRONOUS_IO_ALERT flag must be cleared.

</td>
</tr>
</table>
 


### -param fFlagsAndAttributes [in]

A value that specifies whether the stream is opened for normal or read-only access. This parameter must be set to either 

FILE_ATTRIBUTE_NORMAL or FILE_ATTRIBUTE_READONLY.


### -param fLogOptionFlag [in]

A hint about the relationship between CLFS and the component creating or opening the stream. This parameter must be set to one of the following values:
	 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
CLFS_FLAG_NO_FLAGS

</td>
<td>
CLFS and the creating component have the standard, normal relationship. Kernel-mode components use this value unless they fall into one of the three other categories listed in this table. If <i>pvContext</i> is not <b>NULL</b>, CLFS verifies that <i>cbContext</i> is greater than zero. Otherwise, <i>pvContext</i> and <i>cbContext</i> are ignored.

</td>
</tr>
<tr>
<td>
CLFS_FLAG_REENTRANT_FILE_SYSTEM

</td>
<td>
The creating component is the file system that provides the underlying storage for CLFS. CLFS uses the file system for allocating containers, and the file system uses CLFS streams. In this case, it is possible for the file system to call CLFS and for CLFS to make calls back into the file system on the same thread or different threads. If <i>pvContext</i> is not <b>NULL</b>, CLFS verifies that <i>cbContext</i> is greater than zero. Otherwise, <i>pvContext</i> and <i>cbContext</i> are ignored.

</td>
</tr>
<tr>
<td>
CLFS_FLAG_NON_REENTRANT_FILTER

</td>
<td>
The creating component is a file system filter driver that sends all of its CLFS I/O to a specified level below itself on the filter stack. This option allows a filter driver to create a CLFS log without seeing its own logging I/O. The caller passes the non-<b>NULL</b> target device object in the <i>pvContext</i> parameter with <i>cbContext</i> set to the appropriate size. CLFS uses the <a href="..\ntddk\nf-ntddk-iocreatefilespecifydeviceobjecthint.md">IoCreateFileSpecifyDeviceObjectHint</a> routine to create containers at a targeted level in the I/O filter stack specified by the device object.

</td>
</tr>
<tr>
<td>
CLFS_FLAG_REENTRANT_FILTER

</td>
<td>
The creating component is a file system filter driver that sends all of its CLFS I/O to the top of the filter stack. The filter has a recursive relationship with CLFS because it filters its own logging I/O when CLFS performs any file system operation on its containers. The <i>pvContext</i> parameter provides a means for filters to associate a recognizable context with its CLFS containers as log I/O comes down the filter stack. The <i>cbContext</i> parameter specifies the size of the opaque context in bytes.

</td>
</tr>
<tr>
<td>
CLFS_FLAG_MINIFILTER_LEVEL

</td>
<td>
The creating component is a file system minifilter driver that sends all of its CLFS I/O to a specified level below itself on the filter stack. This option allows a minifilter to create a CLFS log  without seeing its own logging I/O. The caller passes the non-<b>NULL</b> minifilter context object in the <i>pvContext</i> parameter with <i>cbContext</i> set to the appropriate size. CLFS uses the <b>IoCreateFileSpecifyDeviceObjectHint</b> routine to create containers at an altitude (specified within the minifilter context) in the filter manager's minifilter stack. 

</td>
</tr>
</table>
 


### -param pvContext [in, optional]

A pointer to a context. The way the context is interpreted depends on the value passed to <i>fLogOptionsFlag</i>. 


### -param cbContext [in]

The size, in bytes, of the context pointed to by <i>pvContext</i>. If <i>pvContext</i> is not <b>NULL</b>, this parameter must be greater than zero. 


## -returns



<b>ClfsCreateLogFile</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



When you create a CLFS stream, it is backed by an underlying physical CLFS log. The underlying log can be either dedicated (backs only one stream) or multiplexed (backs several streams). A dedicated log cannot be converted to a multiplexed log, and a multiplexed log cannot be converted to a dedicated log.

A physical CLFS log name does not include the .blf extension.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>. 




## -see-also

<a href="..\wdm\nf-wdm-clfscloseandresetlogfile.md">ClfsCloseAndResetLogFile</a>



<a href="..\wdm\nf-wdm-clfsdeletelogfile.md">ClfsDeleteLogFile</a>



<a href="..\wdm\nf-wdm-clfscloselogfileobject.md">ClfsCloseLogFileObject</a>



<a href="..\wdm\nf-wdm-clfsdeletelogbypointer.md">ClfsDeleteLogByPointer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ClfsCreateLogFile routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

