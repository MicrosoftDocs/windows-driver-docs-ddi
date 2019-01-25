---
UID: NE:nfccx._NFC_CX_SEQUENCE
title: "_NFC_CX_SEQUENCE" (nfccx.h)
description: The NFC_CX_SEQUENCE enumeration specifies sequences.
old-location: nfpdrivers\nfc_cx_sequence.htm
tech.root: nfpdrivers
ms.assetid: 752451F9-74FC-48A8-B9B8-2CBD381B91D9
ms.date: 02/15/2018
ms.keywords: "*PNFC_CX_SEQUENCE, NFC_CX_SEQUENCE, NFC_CX_SEQUENCE enumeration [Near-Field Proximity Drivers], PNFC_CX_SEQUENCE, SequenceInitComplete, SequenceMaximum, SequenceNfceeDiscComplete, SequencePreInit, SequencePreNfceeDisc, SequencePreRecovery, SequencePreRfDiscStart, SequencePreRfDiscStop, SequencePreShutdown, SequenceRecoveryComplete, SequenceRfDiscStartComplete, SequenceRfDiscStopComplete, SequenceShutdownComplete, _NFC_CX_SEQUENCE, nfccx/NFC_CX_SEQUENCE, nfccx/SequenceInitComplete, nfccx/SequenceMaximum, nfccx/SequenceNfceeDiscComplete, nfccx/SequencePreInit, nfccx/SequencePreNfceeDisc, nfccx/SequencePreRecovery, nfccx/SequencePreRfDiscStart, nfccx/SequencePreRfDiscStop, nfccx/SequencePreShutdown, nfccx/SequenceRecoveryComplete, nfccx/SequenceRfDiscStartComplete, nfccx/SequenceRfDiscStopComplete, nfccx/SequenceShutdownComplete, nfpdrivers.nfc_cx_sequence"
ms.topic: enum
req.header: nfccx.h
req.include-header: Ncidef.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	nfccx.h
api_name:
-	NFC_CX_SEQUENCE
product:
- Windows
targetos: Windows
req.typenames: NFC_CX_SEQUENCE, *PNFC_CX_SEQUENCE
---

# _NFC_CX_SEQUENCE enumeration


## -description


The NFC_CX_SEQUENCE enumeration specifies sequences.


## -enum-fields




### -field SequencePreInit

This sequence is invoked by CX during the idle to init state transition, that is, prior to start of initialization by NFC CX. No NCI commands including CORE_RESET_CMD have been sent to the NFC controller by NFC CX. In this sequence, the client can invoke any non-NCI command. NCI commands should not be sent to the controller because neither CORE_RESET_CMD nor CORE_INIT_CMD has been sent to the controller.


### -field SequenceInitComplete

This sequence is invoked by CX during the idle to init state transition, that is, prior to start of initialization by NFC CX. No NCI commands including CORE_RESET_CMD has been sent to the NFC controller by NFC CX. In this sequence, the client can invoke any non-NCI command. NCI commands should not be sent to the controller since neither CORE_RESET_CMD nor CORE_INIT_CMD has been sent to the controller.


### -field SequencePreRfDiscStart

This sequence is invoked by CX prior to start of RF discovery i.e. through RF_DISCOVER_CMD. The client driver can use this opportunity to perform any related RF configuration including any optimizations to the discovery loop.


### -field SequenceRfDiscStartComplete

This sequence is invoked by CX immediately after the start of RF discovery. Any configuration post-discovery start can be supported through this extensibility point.


### -field SequencePreRfDiscStop

This sequence is invoked by CX prior to stopping the RF discovery loop.


### -field SequenceRfDiscStopComplete

This sequence is invoked immediately after discovery loop is stopped. The client driver can use this extensibility point to enable any standby mode configuration.


### -field SequencePreNfceeDisc

This sequence is invoked by CX prior to start of NFCEE discovery. The NFCEE discovery happens with the discovery loop deactivated. The client driver can use this sequence to enable any internal NFC-NFCEE interfaces which could have been disabled post-initialization for power optimizations. 


### -field SequenceNfceeDiscComplete

This sequence is invoked immediately post-NFCEE discovery operation.


### -field SequencePreShutdown

This sequence is invoked prior to start of shutdown.


### -field SequenceShutdownComplete

This sequence is invoked by CX after shutdown sequence is complete. The client driver can clean up any NCI state maintained.


### -field SequencePreRecovery

This sequence is invoked by CX if it needs to perform a recovery sequence due to a fatal failure. The client driver can use this sequence to capture RAM dumps for diagnostic purposes.


### -field SequenceRecoveryComplete

This sequence is invoked by the CX after the completion of the recovery sequence and when the driver is back to the work-state.


### -field SequenceMaximum


## -see-also




<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/nfc-class-extension-">NFC class extension design guide</a>



<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>
 

 

