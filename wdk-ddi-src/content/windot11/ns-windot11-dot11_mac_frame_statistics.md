---
UID: NS:windot11.DOT11_MAC_FRAME_STATISTICS
title: DOT11_MAC_FRAME_STATISTICS
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_mac_frame_statistics.htm
old-project: netvista
ms.assetid: 57c75a4c-7224-45d5-af96-6e969548248a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: DOT11_MAC_FRAME_STATISTICS structure [Network Drivers Starting with Windows Vista], PDOT11_MAC_FRAME_STATISTICS structure pointer [Network Drivers Starting with Windows Vista], Native_802.11_data_types_f04e9263-5c70-402b-a2d1-8f4689b4a13e.xml, DOT11_MAC_FRAME_STATISTICS, *PDOT11_MAC_FRAME_STATISTICS, PDOT11_MAC_FRAME_STATISTICS, netvista.dot11_mac_frame_statistics, windot11/PDOT11_MAC_FRAME_STATISTICS, windot11/DOT11_MAC_FRAME_STATISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
-	windot11.h
apiname:
-	DOT11_MAC_FRAME_STATISTICS
product: Windows
targetos: Windows
req.typenames: DOT11_MAC_FRAME_STATISTICS, *PDOT11_MAC_FRAME_STATISTICS
req.product: Windows 10 or later.
---

# DOT11_MAC_FRAME_STATISTICS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_MAC_FRAME_STATISTICS structure records statistical counters for the IEEE media access
  control (MAC) sublayer of the 802.11 station.


## -syntax


````
typedef struct DOT11_MAC_FRAME_STATISTICS {
  ULONGLONG ullTransmittedFrameCount;
  ULONGLONG ullReceivedFrameCount;
  ULONGLONG ullTransmittedFailureFrameCount;
  ULONGLONG ullReceivedFailureFrameCount;
  ULONGLONG ullWEPExcludedCount;
  ULONGLONG ullTKIPLocalMICFailures;
  ULONGLONG ullTKIPReplays;
  ULONGLONG ullTKIPICVErrorCount;
  ULONGLONG ullCCMPReplays;
  ULONGLONG ullCCMPDecryptErrors;
  ULONGLONG ullWEPUndecryptableCount;
  ULONGLONG ullWEPICVErrorCount;
  ULONGLONG ullDecryptSuccessCount;
  ULONGLONG ullDecryptFailureCount;
} DOT11_MAC_FRAME_STATISTICS, *PDOT11_MAC_FRAME_STATISTICS;
````


## -struct-fields




#### - ullTransmittedFrameCount

The number of MAC service data unit (MSDU) packets and MAC management protocol data unit (MMPDU)
     frames that the IEEE MAC sublayer of the 802.11 station successfully transmitted.


#### - ullReceivedFrameCount

The number of MSDU packets and MMPDU frames that the IEEE MAC sublayer of the 802.11 station
     successfully received. This member should not be incremented for received packets that failed cipher
     decryption or MIC validation.


#### - ullTransmittedFailureFrameCount

The number of MSDU packets and MMPDU frames that the IEEE MAC sublayer of the 802.11 station
     failed to transmit successfully.


#### - ullReceivedFailureFrameCount

The number of MSDU packets and MMPDU frames that the IEEE MAC sublayer of the 802.11 station
     failed to receive successfully.


#### - ullWEPExcludedCount

The number of unencrypted received MAC protocol data unit (MPDU) frames that the MAC sublayer
     discarded when the IEEE 802.11 
     <b>dot11ExcludeUnencrypted</b> management information base (MIB) object is enabled. For more information
     about this MIB object, see 
     <a href="https://msdn.microsoft.com/en-us/library/gg159162.aspx">OID_DOT11_EXCLUDE_UNENCRYPTED</a>.
     

MPDU frames are considered unencrypted when the Protected Frame subfield of the Frame Control field
     in the IEEE 802.11 MAC header is set to zero.


#### - ullTKIPLocalMICFailures

The number of received MSDU packets that the 802.11 station discarded because of MIC
     failures.


#### - ullTKIPReplays

The number of received MPDU frames that the 802.11 station discarded because of the TKIP replay
     protection procedure.


#### - ullTKIPICVErrorCount

The number of encrypted MPDU frames that the 802.11 station failed to decrypt because of a TKIP
     ICV error.


#### - ullCCMPReplays

The number of received MPDU frames that the 802.11 station discarded because of the AES-CCMP
     replay protection procedure.


#### - ullCCMPDecryptErrors

The number of received MPDU frames that the 802.11 station discarded because of errors detected by
     the AES-CCMP decryption algorithm.


#### - ullWEPUndecryptableCount

The number of encrypted MPDU frames received for which a WEP decryption key was not available on
     the 802.11 station.


#### - ullWEPICVErrorCount

The number of encrypted MPDU frames that the 802.11 station failed to decrypt because of a WEP ICV
     error.


#### - ullDecryptSuccessCount

The number of received encrypted packets that the 802.11 station successfully decrypted. 
     

For the WEP and TKIP cipher algorithms, the miniport driver must increment this counter for each
     received encrypted MPDU that was successfully decrypted. For the AES-CCMP cipher algorithm, the miniport
     driver must increment this counter on each received encrypted MSDU packet that was successfully
     decrypted.


#### - ullDecryptFailureCount

The number of encrypted packets that the 802.11 station failed to decrypt. 
     

For the WEP and TKIP cipher algorithms, the miniport driver must increment this counter for each
     received encrypted MPDU that was not successfully decrypted. For the AES-CCMP cipher algorithm, the
     miniport driver must increment this counter on each received encrypted MSDU packet that was not
     successfully decrypted.

The miniport driver must not increment this counter for packets that are decrypted successfully, but
     are discarded for other reasons. For example, the miniport driver must not increment this counter for
     packets discarded because of TKIP MIC failures or TKIP/CCMP replays.


## -remarks


The members of the DOT11_MAC_STATISTICS structure are used to record MAC-level statistics for:
<ul>
<li>
802.11 MSDU packets.

</li>
<li>
802.11 MMPDU frames.

</li>
<li>
802.11 MPDU frames. MPDU frame counters must include all MPDU fragments sent for an MSDU packet or
      MMPDU frame

</li>
</ul>


## -see-also

<a href="..\windot11\ns-windot11-dot11_statistics.md">DOT11_STATISTICS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569420">OID_DOT11_STATISTICS</a>

<a href="https://msdn.microsoft.com/e6bd2abf-faa2-463f-91df-a15924afae96">Native 802.11 Statistics</a>

<mshelp:link keywords="netvista.extensible_station_mac_statistics" tabindex="0">Extensible Station MAC
   Statistics</mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_MAC_FRAME_STATISTICS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

