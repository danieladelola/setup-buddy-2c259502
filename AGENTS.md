<!-- LOVABLE:BEGIN -->
> [!IMPORTANT]
> This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
> published git history — force pushing, or rebasing/amending/squashing commits
> that are already pushed — as it rewrites history on Lovable's side and the
> user will likely lose their project history.
>
> Commits you push to the connected branch sync back to Lovable and show up in
> the editor, so keep the branch in a working state.
<!-- LOVABLE:END -->
- Payments use Lenco Pay: browser popup opens with a server-generated reference (`vote-`/`tkt-` prefix), and only `finalizePayment` in src/lib/lenco.server.ts (after re-checking Lenco's status API) marks orders paid — why: the browser callback can be faked.
- Lenco API calls must send a User-Agent header — why: Lenco's Cloudflare firewall returns 403 without one.
