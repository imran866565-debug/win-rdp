# win-rdp — Instant Windows RDP via GitHub Actions + Tailscale

Free Windows PC for up to 6 hours per run. Connect from Android with Tailscale + Microsoft Remote Desktop.

## 1. One-time setup (2 minutes)

1. Tailscale auth key banao:
   - Phone par Tailscale app kholo, ya browser me jao: https://login.tailscale.com/admin/settings/keys
   - Generate auth key > Reusable OFF, Ephemeral ON, Expiry 90 days > Generate
   - Key copy karo (ye sirf ek dafa dikhti hai)
2. GitHub secret add karo:
   - Is repo me jao: Settings > Secrets and variables > Actions > New repository secret
   - Name: `TS_AUTHKEY`
   - Value: upar wali key paste karo > Add secret
3. Optional password (agar khud ka password chahiye):
   - Same jagah ek aur secret: Name `RDP_PASSWORD`, Value apna password
   - Agar ye na banaya to workflow khud ek random password banayega aur run ke log me dikhayega

## 2. Windows chalao

- Repo > Actions > "Windows RDP via Tailscale" > Run workflow > Run workflow
- 2-4 minute me Windows ready ho jayega
- Run ke log me dekho:
  - `Tailscale IP: 100.x.x.x`
  - Username: `runneradmin`
  - Password: `GENERATED_RDP_PASSWORD=...` ya apna `RDP_PASSWORD` secret

## 3. Android se connect karo

1. Phone par Tailscale app ON rakho (same Tailscale account)
2. Microsoft Remote Desktop app install karo (Play Store, free)
3. Add PC > PC name: `100.x.x.x` (log wali IP)
4. User account > Add > Username: `runneradmin`, Password: upar wala password
5. Connect — poora Windows desktop phone par chalega

## Band karna

- GitHub Actions me run ko Cancel kar do, ya 6 ghante baad khud band ho jayega
- Har dafa Run workflow dabao to naya Windows milta hai, purana data save NAHI hota — kaam Drive / GitHub par save karo
