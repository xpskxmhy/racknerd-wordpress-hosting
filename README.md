# RackNerd WordPress hosting: is $5.59/month enough, which shared plan do you actually need, and when is the $18.66/year VPS the better buy?

A normal WordPress blog or small business site runs fine on RackNerd's **Shared 30 GB** plan, listed at **$5.59/month** or **$67.08/year**. You only need to move up the ladder if you're parking several sites or a large media library on the same account. If you want root access, a custom PHP stack, or you're running a WooCommerce store with real concurrent checkout traffic, shared hosting is the wrong product and a KVM VPS is the one to price out (promo listings have had a 2.5 GB plan at $18.66/year).

Below: the three shared plans side by side, the spec difference the price ladder hides, what the $5.59 is actually paying for, where the VPS route wins, and how to get WordPress live on either one.

> **Quick pick**
> - One WordPress site, no terminal, want WAF and daily backups included → Shared 30 GB at $5.59/mo.
> - Several sites or heavy image libraries on one account → Shared 100 GB or 200 GB.
> - Root access, custom caching stack, or a busy store → KVM VPS, and you own the backups.
>
> 👉 [Check what the 30 GB shared plan costs right now](https://bit.ly/RacKnerd)

## The three shared plans, and what the price steps buy you

| Plan | NVMe storage | Monthly transfer | Price | Billing | Order |
| --- | --- | --- | --- | --- | --- |
| Shared 30 GB | 30 GB | 2 TB | $5.59/mo or $67.08/yr | Monthly or annual | [ Get the 30 GB plan](https://bit.ly/RacKnerd) |
| Shared 100 GB | 100 GB | 3 TB | $9.59/mo or $115.08/yr | Monthly or annual | [ Get the 100 GB plan](https://bit.ly/RacKnerd) |
| Shared 200 GB | 200 GB | 5 TB | $15.59/mo or $187.08/yr | Monthly or annual | [ Get the 200 GB plan](https://bit.ly/RacKnerd) |

Pricing reflects a third-party compilation of RackNerd's hosting pages rather than a price I could confirm on an official pricing page, so confirm the figure in the cart before you pay. Third-party copies of the same page also disagree on bandwidth (2 TB versus 3 TB on the entry plan) and on how many add-on domains the 30 GB tier allows, with one listing saying unlimited and another capping it at three total. That last detail matters if you plan to host more than one site on the cheap plan.

The VPS side is a different product line with different numbers. Promo listings have run a **2.5 GB KVM VPS at $18.66/year** (2 vCPU, 45 GB SSD, 3 TB monthly transfer, full root), and standard KVM plans have been listed from around **$21.99/year**. Those are promotional prices from third-party pages, not official quotes, and stock on annual specials comes and goes.

## All three shared plans share the same ceiling

This is the part the price ladder doesn't tell you. One detailed review of the shared lineup reports that every tier carries the **same per-account resource limits: 100% CPU, 1 GB of physical memory and 80 MB/s of I/O**. The only things that change as you pay more are disk space, monthly transfer and (possibly) domain count.

In practice that means a single WordPress site hitting a memory or concurrency wall will hit the same wall on the $15.59 plan as on the $5.59 plan. Upgrading does not make one site faster under load.

How much space does a WordPress site actually eat? A typical install with a theme and around 20 plugins sits at **500 MB to 1 GB**. Most content sites take years to push past 10 GB of real disk usage, even with a few hundred images. On 30 GB you're not going to run out with one blog, a portfolio, or a five-page business site.

So the honest reading of the ladder: 30 GB covers a single site comfortably; 100 GB and 200 GB are for people stacking multiple WordPress installs on one cPanel account, or storing big media libraries, or keeping local backups on disk. If you're buying the 200 GB plan expecting a faster site, you're buying the wrong thing.

## The annual price is the monthly price times twelve

Run the arithmetic and there's no annual discount built in. **$5.59 × 12 = $67.08**. **$9.59 × 12 = $115.08**. **$15.59 × 12 = $187.08**. All three line up exactly with the published annual figures, so the decision is about cash flow and commitment, not about saving a percentage by prepaying.

Paying monthly costs more in admin hassle than in money. Paying annually locks in a year at a company whose renewal pricing I couldn't verify on any page I checked. If you're testing the platform, a month-to-month start at $5.59 tells you more than any review will.

👉 [See all three shared plans and their current billing options](https://bit.ly/RacKnerd)

## What the $5.59 is actually paying for

The shared platform was rebuilt on **AMD Ryzen 7950X** processors (5.7 GHz boost, and single-core speed is what drives WordPress PHP execution) with **NVMe Gen4** storage, running **CloudLinux 9** so each account sits in its own container with separate CPU, RAM and I/O caps. The web server is **LiteSpeed Enterprise** with LSCache, which means full-page caching happens at the server level before a request ever reaches PHP. A free **cpGuard WAF** is included, which matters for WordPress specifically because login brute-forcing and plugin vulnerability scans are constant background noise. **JetBackup** handles daily off-site backups, and **KernelCare** patches the kernel without a reboot.

Price out those licences separately and the math gets interesting. LiteSpeed Enterprise alone runs about **$25+/month**, CloudLinux around **$12/month**, cpGuard about **$17/month** ($200+/year), and cPanel typically **$15–20/month**. RackNerd bundles all of it into a $5.59 plan. That's the actual argument for this host, more than any benchmark.

The limits are worth stating plainly. This is **not managed WordPress**. The host doesn't push core updates for you and there's no built-in staging environment. You get cPanel, Softaculous, and infrastructure. Updates, plugin conflicts and broken layouts are yours.

Support is 24/7 ticket-based with an average first response around 10 minutes, and SSL not loading, email setup and migration help tend to resolve in one or two replies. Nothing deeper than that is covered.

## When the VPS is the right purchase

A RackNerd KVM VPS is unmanaged. When a plugin update takes the site down at 2 a.m., you're the one SSHing in. Support covers network outages, hardware failures and billing, not why WooCommerce checkout throws a fatal error. There's also **no backup by default** on a VPS, unlike the shared plans with JetBackup, so you'll want UpdraftPlus or a server-side script pushing copies somewhere off the box.

What you get in exchange: full root, any PHP version and caching stack you like, no plugin restrictions, and dedicated RAM. Around 20 datacenter locations are available, and for European audiences Amsterdam or London cuts roughly **100–150 ms** per request compared with US East, according to one reviewer's estimate. Upgrades happen in place, with a reboot and about a minute of downtime, keeping the same IP and data.

|  | Shared (cPanel) | KVM VPS |
| --- | --- | --- |
| Root access | No | Yes |
| Backups | JetBackup, daily, off-site | None by default |
| Stack | LiteSpeed + LSCache, preconfigured | Whatever you install |
| Updates and fixes | You | You |
| Best for | One to a few standard sites | Custom stacks, heavy or concurrent workloads |

👉 [Compare RackNerd's current shared and VPS plan listings](https://bit.ly/RacKnerd)

## Getting WordPress live on shared hosting

Ordering takes a few minutes and the account activates right after payment. The welcome email carries your cPanel login.

1. Open cPanel and find **Softaculous Apps Installer** under Software.
2. Pick WordPress, then Install Now. Enter domain, site name, admin username, admin email and a password. Leave the directory blank to install at the root.
3. The install finishes in under a minute and your dashboard is at `yourdomain.com/wp-admin`.
4. Install the free **LiteSpeed Cache** plugin from the WordPress directory. It activates the server-level caching your account is already licensed for, with no configuration needed.
5. Point the domain's nameservers at the ones in your welcome email. DNS propagation takes 1–24 hours.

Shared hosting datacenter choices at checkout are Los Angeles, New York City, Frankfurt, Strasbourg and Singapore. Pick the one closest to your readers rather than defaulting to LA.

👉 [Start a shared hosting order and get the cPanel details by email](https://bit.ly/RacKnerd)

## Getting WordPress live on a VPS with the official one-line script

RackNerd's own blog documents a LOMP install (Linux, OpenLiteSpeed, MariaDB, LS-PHP) using LiteSpeed Technologies' official installer, not a third-party script. Pick Ubuntu 22.04 or 24.04 LTS at checkout unless you specifically want AlmaLinux, then SSH in as root.

bash
dnf update -y    # or apt update && apt upgrade on Ubuntu
bash <( curl -k https://raw.githubusercontent.com/litespeedtech/ols1clk/master/ols1clk.sh ) -w


Choose OpenLiteSpeed, LS-PHP, MariaDB, WordPress and LiteSpeed Cache in the wizard, and save the database and admin credentials it prints. Then check the service and open the firewall:

bash
systemctl status lsws
systemctl enable --now lsws
firewall-cmd --permanent --add-port={8088,7080,80,443}/tcp && firewall-cmd --reload


The OpenLiteSpeed admin console is at `http://your-server-ip:7080` (default username `admin`), and you finish the WordPress install at `http://your-server-ip`. If the response headers show `Server: LiteSpeed`, the stack is running. Add Let's Encrypt SSL with CertBot afterwards. A first run through this takes an afternoon if you're learning; the third time it's a coffee break.

## Three lines in wp-config.php that fix most WordPress emergencies

RackNerd's own walkthrough covers the fixes you can do yourself in cPanel's File Manager, no reinstall needed. Open `public_html/wp-config.php` (or your subfolder), right-click, Edit.

**Database connection errors:** check `DB_NAME`, `DB_USER`, `DB_PASSWORD` and `DB_HOST` against the values in your hosting account. One wrong character produces the "Error establishing a database connection" page.

**Blank white screen:** find `WP_DEBUG` and change `false` to `true` so WordPress prints the actual error and names the plugin or theme responsible. Turn it back to `false` once you've fixed it, so visitors don't see the notices.

**"Allowed memory size exhausted":** just above the `/* That's it. Stop editing. Happy blogging. */` line, add a line raising the limit to 256 MB, which covers most sites with heavier themes and plugin stacks.

Save, close, refresh the site.

## FAQ

**Can the shared plans run WooCommerce?**
A small catalog with modest traffic, yes. Complex product filtering, real-time inventory lookups and heavy concurrent checkout traffic aren't a shared hosting use case at any tier, because the RAM and I/O ceiling is the same across all three plans. That's VPS territory.

**How many WordPress sites fit in 30 GB?**
By storage, several, since each site is 500 MB–1 GB. By account limits, the shared resource cap is the binding constraint, and one third-party listing says the 30 GB tier only allows three domains total. Check the cart if you're planning a small network.

**Is $5.59 a first-year price? Will it renew higher?**
I couldn't verify renewal pricing on any page I checked, and no source I found documents a renewal increase or a lock-in. The cart shows the billing term and the amount due; read it before paying, and ask support directly if a fixed multi-year rate matters to you.

**Do I need root access?**
Only if you want a custom web stack, a specific PHP build, server-level tuning, or software that cPanel won't run. Standard WordPress on LiteSpeed with a caching plugin doesn't require it.

**Which datacenter should European or Asian readers choose?**
Shared hosting offers Frankfurt, Strasbourg and Singapore alongside LA and NYC. On the VPS side, Amsterdam or London are the sensible European picks; one reviewer estimates 100–150 ms saved per request versus US East.

**Is there a money-back guarantee?**
I found no verified refund window on the pages I checked, so I won't quote one. If a trial period is a condition of your purchase, ask support before you pay.

## Pick by site count, not by price

One WordPress site, no terminal, wanting backups and a WAF handled for you: **Shared 30 GB at $5.59/month**. Several installs or a media-heavy site on one account: **100 GB or 200 GB**, since storage is the only thing that changes. Custom stack, root access, or a store with real concurrency: **KVM VPS**, with a backup routine you set up yourself. And if you'd rather never touch a server or an update again, none of these fit; that's managed WordPress hosting, at several times the price.

Two things to check in the cart before you pay: the billing term you're actually selecting, and the bandwidth and domain allowance on your chosen tier, because third-party copies of the page disagree on both.

👉 [Pick the RackNerd plan that matches your site count](https://bit.ly/RacKnerd)
