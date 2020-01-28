---
UID: NS:windot11.DOT11_MAC_FRAME_STATISTICS
title: DOT11_MAC_FRAME_STATISTICS (windot11.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_mac_frame_statistics.htm
tech.root: netvista
ms.assetid: 57c75a4c-7224-45d5-af96-6e969548248a
ms.date: 02/16/2018
ms.keywords: "*PDOT11_MAC_FRAME_STATISTICS, DOT11_MAC_FRAME_STATISTICS, DOT11_MAC_FRAME_STATISTICS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_f04e9263-5c70-402b-a2d1-8f4689b4a13e.xml, PDOT11_MAC_FRAME_STATISTICS, PDOT11_MAC_FRAME_STATISTICS structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_mac_frame_statistics, windot11/DOT11_MAC_FRAME_STATISTICS, windot11/PDOT11_MAC_FRAME_STATISTICS"
f1_keywords:
 - "windot11/DOT11_MAC_FRAME_STATISTICS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- windot11.h
api_name:
- DOT11_MAC_FRAME_STATISTICS
targetos: Windows
req.typenames: DOT11_MAC_FRAME_STATISTICS, *PDOT11_MAC_FRAME_STATISTICS
product:
- Windows 10 or later.
---

# DOT11_MAC_FRAME_STATISTICS structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_MAC_FRAME_STATISTICS structure records statistical counters for the IEEE media access
  control (MAC) sublayer of the 802.11 station.


## -syntax


```cpp
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
```


## -struct-fields




### -field ullTransmittedFrameCount

The number of MAC service data unit (MSDU) packets and MAC management protocol data unit (MMPDU)
     frames that the IEEE MAC sublayer of the 802.11 station successfully transmitted.


### -field ullReceivedFrameCount

The number of MSDU packets and MMPDU frames that the IEEE MAC sublayer of the 802.11 station
     successfully received. This member should not be incremented for received packets that failed cipher
     decryption or MIC validation.


### -field ullTransmittedFailureFrameCount

The number of MSDU packets and MMPDU frames that the IEEE MAC sublayer of the 802.11 station
     failed to transmit successfully.


### -field ullReceivedFailureFrameCount

The number of MSDU packets and MMPDU frames that the IEEE MAC sublayer of the 802.11 station
     failed to receive successfully.


### -field ullWEPExcludedCount

The number of unencrypted received MAC protocol data unit (MPDU) frames that the MAC sublayer
     discarded when the IEEE 802.11
     <b>dot11ExcludeUnencrypted</b> management information base (MIB) object is enabled. For more information
     about this MIB object, see
     <a href="https://docs.microsoft.com/previous-versions/windows/embedded/gg159162(v=winembedded.80)">OID_DOT11_EXCLUDE_UNENCRYPTED</a>.


MPDU frames are considered unencrypted when the Protected Frame subfield of the Frame Control field
     in the IEEE 802.11 MAC header is set to zero.


### -field ullTKIPLocalMICFailures

The number of received MSDU packets that the 802.11 station discarded because of MIC
     failures.


### -field ullTKIPReplays

The number of received MPDU frames that the 802.11 station discarded because of the TKIP replay
     protection procedure.


### -field ullTKIPICVErrorCount

The number of encrypted MPDU frames that the 802.11 station failed to decrypt because of a TKIP
     ICV error.


### -field ullCCMPReplays

The number of received MPDU frames that the 802.11 station discarded because of the AES-CCMP
     replay protection procedure.


### -field ullCCMPDecryptErrors

The number of received MPDU frames that the 802.11 station discarded because of errors detected by
     the AES-CCMP decryption algorithm.


### -field ullWEPUndecryptableCount

The number of encrypted MPDU frames received for which a WEP decryption key was not available on
     the 802.11 station.


### -field ullWEPICVErrorCount

The number of encrypted MPDU frames that the 802.11 station failed to decrypt because of a WEP ICV
     error.


### -field ullDecryptSuccessCount

The number of received encrypted packets that the 802.11 station successfully decrypted.


For the WEP and TKIP cipher algorithms, the miniport driver must increment this counter for each
     received encrypted MPDU that was successfully decrypted. For the AES-CCMP cipher algorithm, the miniport
     driver must increment this counter on each received encrypted MSDU packet that was successfully
     decrypted.


### -field ullDecryptFailureCount

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-dot11-statistics">OID_DOT11_STATISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/extensible-station-mac-statistics">Extensible Station MAC
   Statistics</a>



<a href="..\windot11\ns-windot11-dot11_statistics.md">DOT11_STATISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/native-802-11-statistics">Native 802.11 Statistics</a>



 

 


