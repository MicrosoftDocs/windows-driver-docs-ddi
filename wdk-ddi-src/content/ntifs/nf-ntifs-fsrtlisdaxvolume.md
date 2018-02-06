---
UID: NF:ntifs.FsRtlIsDaxVolume
title: FsRtlIsDaxVolume function
author: windows-driver-content
description: This routine queries if the specified file is on a direct access (DAX) volume.
old-location: ifsk\fsrtlisdaxvolume.htm
old-project: ifsk
ms.assetid: FFCD2329-FD6A-48AE-8E9D-56AA7D79B174
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.fsrtlisdaxvolume, FsRtlIsDaxVolume, ntifs/FsRtlIsDaxVolume, FsRtlIsDaxVolume routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
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
req.lib: NtosKrnl.exe
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
-	FsRtlIsDaxVolume
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlIsDaxVolume function


## -description


This routine queries if the specified file is on a  direct access (DAX) volume.


## -syntax


````
BOOLEAN FsRtlIsDaxVolume(
  _In_ PFILE_OBJECT FileObject
);
````


## -parameters




### -param FileObject [in]

A file object for a file, on the volume which is being queried.


## -returns


Returns <b>true</b> if the file is on a DAX volume; otherwise, <b>false</b>.



## -remarks


In DAX volumes,  user files
    are mapped directly to the persistent memory device.  Files are
    then accessed using the memory bus, to help boost system performance.


