# COMP5002 CW1 – Evidence Portfolio

Evidence for the intrusion analysis report *Cerber Ransomware via RIG Exploit Kit*.
All screenshots were taken in Wireshark from the supplied capture `COMP5002 CW1.pcap`
(27 January 2017, 22:53:08–22:59:51 UTC). The investigation steps that produce each
figure are listed in Appendix B (Investigation log) of the report.

## Figures

| Figure | File | Shows | Log step |
| --- | --- | --- | --- |
| 1 | [fig01-capture-properties.png](figures/fig01-capture-properties.png) | Capture File Properties: 6,033 packets, 22:53:08–22:59:51 UTC on 2017-01-27 (Q1) | 3 |
| 2 | [fig02-endpoints.png](figures/fig02-endpoints.png) | Endpoints limited to HTTP requests to RIG server 194.87.234.129; all from 172.16.4.193 (Q3) | 1 |
| 3 | [fig03-mac-address.png](figures/fig03-mac-address.png) | Frame 2, Ethernet II: source MAC Dell_02:a8:e4 (5c:26:0a:02:a8:e4) (Q4) | 2 |
| 4 | [fig04-dhcp-hostname.png](figures/fig04-dhcp-hostname.png) | DHCP frame 19: IP 172.16.4.193, MAC 5c:26:0a:02:a8:e4, host name Stewie-PC (Q5) | 2 |
| 5 | [fig05-gate-dle-js.png](figures/fig05-gate-dle-js.png) | HTTP stream 43: homeimprovement.com loads dle_js.js from the gate, which writes an off-screen iframe to tyu.benme.com (Q10) | 5 |
| 6 | [fig06-frame2852-time.png](figures/fig06-frame2852-time.png) | Frame 2852, first request to the RIG server, at 22:54:43 UTC (Q2) | 3 |
| 7 | [fig07-rig-frame2896.png](figures/fig07-rig-frame2896.png) | Requests to tyu.benme.com; frame 2896 shows the RIG URL pattern, Referer and IE11 User-Agent (Q9) | 6 |
| 8 | [fig08-udp-6892-beacon.png](figures/fig08-udp-6892-beacon.png) | Conversations filtered to udp.port == 6892: 1,152 packets to 576 addresses, no replies – Cerber beacon (Q6) | 8 |
| 9 | [fig09-top-portal.png](figures/fig09-top-portal.png) | HTTP stream 55 at 22:55:28 UTC: Cerber portal p27dokhpz2n7nvgr.1jw2lx.top contacted with an MSIE 7.0 User-Agent (Q7) | 7, 11 |
| 10 | [fig10-cerber-decryptor.png](figures/fig10-cerber-decryptor.png) | HTTP stream 65 (filter http.file_data contains "Cerber"): page titled "Cerber Decryptor" at 22:56:54 UTC (Q8) | 10 |
| 11 | [fig11-msdownload-payloads.png](figures/fig11-msdownload-payloads.png) | Export Objects filtered to application/x-msdownload: three executables, all from tyu.benme.com | 7, 12 |
| 12 | [fig12-mz-check.png](figures/fig12-mz-check.png) | Frame 3422 payload starts 3d 7c 69 7e ("=\|i~"), not 4d 5a ("MZ"): delivered encoded | 13 |
| 13 | [fig13-spotsbill.png](figures/fig13-spotsbill.png) | HTTP stream 53, frame 3824: spotsbill.com check-in with MSIE 7.0 User-Agent; encoded response | 14 |

Figures 12 and 13 were annotated with AI assistance (see Appendix E of the report).

## AI use logs

- Claude conversation (commercial model): [add share link here]
- Gemma 4 terminal transcript (open-source, run locally): [ai-logs/gemma4-transcript.txt](ai-logs/gemma4-transcript.txt)

## Safety note

No malware samples or extracted payloads are included in this repository.
