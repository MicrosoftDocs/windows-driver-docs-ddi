---
UID: NS:avcstrm._DVINFO
title: "_DVINFO"
author: windows-driver-content
description: The DVINFO structure describes a DV stream format including its default streaming source information and stream control information.
old-location: stream\dvinfo.htm
old-project: stream
ms.assetid: 3afd372f-556f-4c3a-804b-9bf7a8c9a438
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PDVINFO, ,, D, DVINFO, DVINFO structure [Streaming Media Devices], F, I, N, O, P, PDVINFO, PDVINFO structure pointer [Streaming Media Devices], V, _, _DVINFO, avcsref_9e5ce103-400a-4cfd-b160-5eb99906a80d.xml, avcstrm/DVINFO, avcstrm/PDVINFO, stream.dvinfo"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avcstrm.h
req.include-header: Avcstrm.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	avcstrm.h
apiname:
-	DVINFO
product: Windows
targetos: Windows
req.typenames: DVINFO, *PDVINFO
---

# _DVINFO structure


## -description


The DVINFO structure describes a DV stream format including its default streaming source information and stream control information.


## -syntax


````
typedef struct _DVINFO {
  DWORD dwDVAAuxSrc;
  DWORD dwDVAAuxCtl;
  DWORD dwDVAAuxSrc1;
  DWORD dwDVAAuxCtl1;
  DWORD dwDVVAuxSrc;
  DWORD dwDVVAuxCtl;
  DWORD dwDVReserved[2];
} DVINFO, *PDVINFO;
````


## -struct-fields




### -field dwDVAAuxSrc

Specifies the Audio Auxiliary Data Source Pack for the first audio block (first 5 DV DIF sequences for 525-60 systems or 6 DV DIF sequences for 625-50 systems) of a frame. A DIF sequence is a data block that contains 150 DIF blocks. A DIF block consists of 80 bytes. The Audio Auxiliary Data Source Pack is defined in section D.7.1 of Part 2, Annex D, "The Pack Header Table and Contents of Packs" of the <i>Specification of Consumer-use Digital VCRs</i>.


### -field dwDVAAuxCtl

Specifies the Audio Auxiliary Data Source Control Pack for the first audio block of a frame. The Audio Auxiliary Data Control Pack is defined in section D.7.2 of Part 2, Annex D, "The Pack Header Table and Contents of Packs" of the <i>Specification of Consumer-use Digital VCRs</i>.


### -field dwDVAAuxSrc1

Specifies the Audio Auxiliary Data Source Pack for the second audio block (second 5 DV DIF sequences for 525-60 systems or 6 DV DIF sequences for 625-50 systems) of a frame.


### -field dwDVAAuxCtl1

Specifies the Audio Auxiliary Data Source Control Pack for the second audio block of a frame.


### -field dwDVVAuxSrc

Specifies the Video Auxiliary Data Source Pack as defined in section D.8.1 of Part 2, Annex D, "The Pack Header Table and Contents of Packs" of the <i>Specification of Consumer-use Digital VCRs</i>.


### -field dwDVVAuxCtl

Specifies the Video Auxiliary Data Source Control Pack as defined in section D.8.2 of Part 2, Annex D, "The Pack Header Table and Contents of Packs" of the <i>Specification of Consumer-use Digital VCRs</i>. 


### -field dwDVReserved

Reserved. This must be set to 0. Do not use this.

