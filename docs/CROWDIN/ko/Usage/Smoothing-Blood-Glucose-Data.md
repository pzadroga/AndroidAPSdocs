(Smoothing-Blood-Glucose-Data)=

# 혈당 데이터 평활화

If BG data is jumpy/noisy AAPS may dose insulin incorrectly resulting in high or low BG. If you observe errors in your CGM data it is important to disable the loop until the problem is resolved. Depending on your CGM such issues may be due to the CGM configuration or sensor problems/site issues. You may need to replace your CGM sensor to resolve this.

Some CGM systems have internal algorithms to detect the noise level in the readings and AAPS can use this information to avoid giving SMBs if the BG data is too unreliable. However, some CGMs do not transmit this data and for these BG sources 'Enable SMB always' and 'Enable SMB after carbs' are disabled for safety reasons.

Additionally, as of version 3.2, AAPS offers the option to smooth the data within AAPS. There are three options:

\##Exponential smoothing

This is the recommended option to start with as it is most aggressive in resolving noise and rewrites the most recent value.

\##Average smoothing

This option works similar to back smoothing that was previously implemented on certain CGM platforms. It is more reactive to recent changes in BG value and therefore more prone to responding incorrectly to noisy CGM data.

\##No Smoothing

Use this option only if your CGM data is being properly smoothed by your collector app beore being transmitted to AAPS.
