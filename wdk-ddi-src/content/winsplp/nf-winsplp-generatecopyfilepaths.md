---
UID: NF:winsplp.GenerateCopyFilePaths
title: GenerateCopyFilePaths function
author: windows-driver-content
description: A Point and Print DLL's GenerateCopyFilePaths function is used for modifying the source and destination paths used by print spoolers when they copy print queue-associated files to a print client.
old-location: print\generatecopyfilepaths.htm
old-project: print
ms.assetid: 61274493-1ec4-483b-85fa-f6087cf0631e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GenerateCopyFilePaths, GenerateCopyFilePaths function [Print Devices], poprfnc_35a0e3c2-1841-4e84-b980-c3b13592c854.xml, print.generatecopyfilepaths, winsplp/GenerateCopyFilePaths
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
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
req.lib: Mscms.lib
req.dll: Mscms.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Mscms.dll
api_name:
-	GenerateCopyFilePaths
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# GenerateCopyFilePaths function


## -description


A Point and Print DLL's <b>GenerateCopyFilePaths</b> function is used for modifying the source and destination paths used by print spoolers when they copy print queue-associated files to a print client.


## -syntax


````
DWORD GenerateCopyFilePaths(
  _In_    LPCWSTR pszPrinterName,
  _In_    LPCWSTR pszDirectory,
  _In_    LPBYTE  pSplClientInfo,
  _In_    DWORD   dwLevel,
  _Inout_ LPWSTR  pszSourceDir,
  _Inout_ LPDWORD pcchSourceDirSize,
  _Inout_ LPWSTR  pszTargetDir,
  _Inout_ LPDWORD pcchTargetDirSize,
  _In_    DWORD   dwFlags
);
````


## -parameters




### -param pszPrinterName [in]

Caller-supplied pointer to a string representing the name of the print queue.


### -param pszDirectory [in]

Caller-supplied pointer to a string representing the value supplied for the server's <b>Directory</b> entry in the registry. For more information, see <a href="https://msdn.microsoft.com/70e65c7b-bba2-4da1-ac80-9719f8005c50">Supporting Point and Print During Printer Installations</a>.


### -param pSplClientInfo [in]

Caller-supplied pointer to an <a href="..\winsplp\ns-winsplp-_splclient_info_1.md">SPLCLIENT_INFO_1</a> structure.


### -param dwLevel [in]

Caller-supplied value indicating the level number of the structure pointed to by <i>pSplClientInfo</i>. Must be 1.


### -param pszSourceDir [in, out]

For input, receives a caller-supplied pointer to a string representing the complete server directory path (including server name) from which files are to be copied.

For output, the function can modify this string.


### -param pcchSourceDirSize [in, out]

Caller-supplied address containing the length of the buffer pointed to by <i>pszSourceDir</i>. (Note that this is the buffer length, not the string length.)


### -param pszTargetDir [in, out]

For input, receives a caller-supplied pointer to a string representing the client directory path to which files are to be copied. The following rules apply:

<ul>
<li>
When the function is called on the server, this path is relative to PRINT$.

</li>
<li>
When the function is called on the client, the string contains a complete path.

</li>
</ul>
For output, the function can modify this string.


### -param pcchTargetDirSize [in, out]

Caller-supplied address containing the length of the buffer pointed to by <i>pszTargetDir</i>. (Note that this is the buffer length, not the string length.)


### -param dwFlags [in]

Caller-supplied flag. Can be one of the following:





#### COPYFILE_FLAG_CLIENT_SPOOLER

Indicates the function is being called by the client's spooler.



#### COPYFILE_FLAG_SERVER_SPOOLER

Indicates the function is being called by the server's spooler.


## -returns



If the operation succeeds, the function should return <b>ERROR_SUCCESS</b>. Otherwise, it should return an error code defined in winerror.h.




## -remarks



All <a href="https://msdn.microsoft.com/7ead940e-8426-4756-890f-f3607dc1f9ca">Point and Print DLLs</a> must export a <b>GenerateCopyFilePaths</b> function, which is called by the print spooler. Its purpose is to allow a Point and Print DLL to modify the source or destination directory path, or both, before the print spooler copies print queue-associated files from a server to a client. (The files are copied when a client connects to a print server. For a complete description of the steps involved in creating a Point and Print connection, see <a href="https://msdn.microsoft.com/a41bed5e-a006-4b9e-aa71-d2bcd154fae2">Supporting Point and Print</a>.)

A Point and Print DLL executes on both the server and the client. The <b>GenerateCopyFilePaths</b> function should check the <i>dwFlags</i> argument to determine where it is executing.

Typically, this function is used to provide compatibility when different versions of the operating system are executing on the client and server. For example if the function, when executing on the server, determines (by reading the <a href="..\winsplp\ns-winsplp-_splclient_info_1.md">SPLCLIENT_INFO_1</a> structure) that its operating system is newer than the client's, it can modify the source and destination paths to be compatible with the client's older OS. On the other hand, if the function determines that the client's operating system is newer than the client's, it should probably do nothing on the server and perform modifications, if necessary, when executing on the client.

Arguments for the <i>pszSourceDir</i> and <i>pszTargetDir</i> parameters point to buffers containing strings that represent the current source and destination directory paths. If modifications to either of these strings is necessary, the function should make modifications in the supplied buffers. The maximum allowable string lengths are pointed to by the <i>pcchSourceDirSize</i> and <i>pcchTargetDirSize</i> arguments.

If no modifications to the source or destination directories are needed, the function should just return <b>ERROR_SUCCESS</b>.




## -see-also

<a href="..\winsplp\nf-winsplp-spoolercopyfileevent.md">SpoolerCopyFileEvent</a>



 

 


