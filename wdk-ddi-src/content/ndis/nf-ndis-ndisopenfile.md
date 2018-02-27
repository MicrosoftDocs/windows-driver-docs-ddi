---
UID: NF:ndis.NdisOpenFile
title: NdisOpenFile function
author: windows-driver-content
description: The NdisOpenFile function returns a handle for an opened file.
old-location: netvista\ndisopenfile.htm
old-project: netvista
ms.assetid: 48d54092-d055-449c-a409-829213db2989
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisOpenFile, NdisOpenFile function [Network Drivers Starting with Windows Vista], ndis/NdisOpenFile, ndis_file_ref_0931368e-111b-4b25-a42d-12d0cc5d9d44.xml, netvista.ndisopenfile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisOpenFile (NDIS 5.1)) in Windows   Vista. Supported for NDIS 5.1 drivers (see    NdisOpenFile (NDIS 5.1)) in Windows   XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisOpenFile
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisOpenFile function


## -description


The
  <b>NdisOpenFile</b> function returns a handle for an opened file.


## -syntax


````
VOID NdisOpenFile(
  _Out_ PNDIS_STATUS          Status,
  _Out_ PNDIS_HANDLE          FileHandle,
  _Out_ PUINT                 FileLength,
  _In_  PNDIS_STRING          FileName,
  _In_  NDIS_PHYSICAL_ADDRESS HighestAcceptableAddress
);
````


## -parameters




### -param Status [out]

A pointer to a caller-supplied variable in which this function returns the status of the open file
     operation, which can be one of the following:
     





#### NDIS_STATUS_SUCCESS

The handle at 
       <i>FileHandle</i> is valid for a subsequent call to 
       <b>NdisMapFile</b>.



#### NDIS_STATUS_FILE_NOT_FOUND

The given string at 
       <i>FileName</i> did not specify a name found in the system object namespace.



#### NDIS_STATUS_RESOURCES

NDIS could not allocate the resources it needed to open the file and allocate a buffer for the
       file contents.



#### NDIS_STATUS_ERROR_READING_FILE

The specified file's data could not be read into system memory for subsequent access by the
       caller.


### -param FileHandle [out]

A pointer to a caller-supplied variable in which this function returns the handle of the opened
     file if the call succeeds.


### -param FileLength [out]

A pointer to a caller-supplied variable in which this function writes the number of bytes of data
     in the opened file if the call succeeds.


### -param FileName [in]

A pointer to an NDIS_STRING type containing an initialized counted string, in the system-default
     character set, naming the file to be opened. For Windows 2000 and later drivers, this string contains
     Unicode characters. That is, for Windows 2000 and later, NDIS defines the NDIS_STRING type as a 
     <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> type.


### -param HighestAcceptableAddress [in]

The highest physical address in which the file data can be stored, or specifies -1 if the driver
     places no restrictions.


## -returns



None




## -remarks



<b>NdisOpenFile</b> opens a disk file, typically a file the driver will later download to program an
    intelligent NIC. 
    <b>NdisOpenFile</b> also allocates storage to hold file contents for the driver's subsequent call to the 
    <a href="..\ndis\nf-ndis-ndismapfile.md">NdisMapFile</a> function.

A miniport driver should call 
    <b>NdisOpenFile</b> only from the 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.

When 
    <b>NdisOpenFile</b> returns, the miniport driver can access file data by calling 
    <b>NdisMapFile</b>. It can call the 
    <a href="..\ndis\nf-ndis-ndisunmapfile.md">NdisUnmapFile</a> function to page out the file
    so it does not consume resources unnecessarily while the driver is not accessing the file data. When
    finished using the file, 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> must call the
    
    <a href="..\ndis\nf-ndis-ndisclosefile.md">NdisCloseFile</a> function.




## -see-also

<a href="..\ndis\nf-ndis-ndismapfile.md">NdisMapFile</a>



<a href="..\ndis\nf-ndis-ndisunmapfile.md">NdisUnmapFile</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisclosefile.md">NdisCloseFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisOpenFile function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

