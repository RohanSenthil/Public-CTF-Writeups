# Script Kiddies [183 Points]

To find out more about the vaccine that the Pentagon has developed, you decide to hack their website. It is not necessary to be an IT expert to hack a website. Important: please do not hack the actual Pentagon website.

https://scriptkiddie.nypinfsecctf.tk/

## Solution

1. Ctrl + U to View Page Source
2. We analyse the script and realise we need to change the text of a HTML element and click a button to view the flag
```
<script>
          function omega() {
            if (document.getElementById('coolkid').innerText === 'scriptkiddie') {
              var unknown = "DND1K_TP1RCS4VNP4JY{13}ASDJHASDBI748ASDB07DFUIMV3JM_19120{12}";
              0123456789
              document.getElementById('skript').innerHTML = unknown[1] + unknown[18] + unknown[15] + unknown[19]
                + unknown[17] + unknown[12] + unknown[13] + unknown[12] + unknown[11] + unknown[10] + unknown[9] + unknown[8] + unknown[15] + unknown[6] + unknown[5]
                + unknown[4] + unknown[8] + unknown[0] + unknown[2] + unknown[3] + unknown[21] + unknown[22];
            }
          }
</script>
```
3. Inspect element and change the text of the HTML element with the id 'coolkid', to 'scriptkiddie'
4. Click on the button to view flag
```
Flag: NYP{J4V4SCR1PT_K1DD13}
```
