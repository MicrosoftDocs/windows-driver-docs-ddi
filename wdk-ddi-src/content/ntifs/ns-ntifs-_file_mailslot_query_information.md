---
UID: NS:ntifs._FILE_MAILSLOT_QUERY_INFORMATION
title: "_FILE_MAILSLOT_QUERY_INFORMATION"
author: windows-driver-content
description: The FILE_MAILSLOT_QUERY_INFORMATION structure contains information about a mailslot.
old-location: ifsk\file_mailslot_query_information.htm
old-project: ifsk
ms.assetid: 8e3b782a-fe8c-42e1-9786-5f89831b4c10
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ifsk.file_mailslot_query_information, ntifs/FILE_MAILSLOT_QUERY_INFORMATION, _FILE_MAILSLOT_QUERY_INFORMATION, PFILE_MAILSLOT_QUERY_INFORMATION, FILE_MAILSLOT_QUERY_INFORMATION, ntifs/PFILE_MAILSLOT_QUERY_INFORMATION, FILE_MAILSLOT_QUERY_INFORMATION structure [Installable File System Drivers], PFILE_MAILSLOT_QUERY_INFORMATION structure pointer [Installable File System Drivers], *PFILE_MAILSLOT_QUERY_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating system.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	FILE_MAILSLOT_QUERY_INFORMATION
product: Windows
targetos: Windows
req.typenames: FILE_MAILSLOT_QUERY_INFORMATION, *PFILE_MAILSLOT_QUERY_INFORMATION
---

# _FILE_MAILSLOT_QUERY_INFORMATION structure


## -description


The <b>FILE_MAILSLOT_QUERY_INFORMATION</b> structure contains information about a  mailslot.


## -syntax


````
typedef struct _FILE_MAILSLOT_QUERY_INFORMATION {
  ULONG         MaximumMessageSize;
  ULONG         MailslotQuota;
  ULONG         NextMessageSize;
  ULONG         MessagesAvailable;
  LARGE_INTEGER ReadTimeout;
} FILE_MAILSLOT_QUERY_INFORMATION, *PFILE_MAILSLOT_QUERY_INFORMATION;
````


## -struct-fields




### -field MaximumMessageSize


The maximum size, in bytes, of a single message that can be written to the mailslot, or 0 for a message of any size.



### -field MailslotQuota


The size, in bytes, of the in-memory pool that is reserved for writes to this mailslot. 



### -field NextMessageSize

The next message size, in bytes.



### -field MessagesAvailable



The total number of messages waiting to be read from the mailslot.



### -field ReadTimeout

  
The time, in milliseconds, that a read operation can wait for a message to be written to the mailslot before a time-out occurs. A value of –1 requests that the read wait forever for a message, without timing out. A value of 0 requests that the read not wait and return immediately whether a pending message is available to be read or not.



## -remarks



For more information, see <a href="https://msdn.microsoft.com/e23894ca-edc7-49e6-bcc4-c82f357ecedf">Mailslots</a>.



