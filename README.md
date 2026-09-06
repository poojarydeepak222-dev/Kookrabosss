# ResultsHub

Mobile-first public results and community forum website.

## Included
- Public result history
- Market search
- Historical result chart
- Supabase email/password login and registration
- Forum posts and comments
- Admin-only result publishing
- Admin-only forum moderation
- GitHub Pages deployment workflow

## Supabase
This site uses the existing Supabase project `bjxbqhcgdwmluwjfawse` in the India region. `config.js` contains only the public publishable key. Never add a service_role key to the repository.

The database already contains `profiles`, `results`, `forum_posts`, and `forum_comments`, with RLS policies. A signup trigger creates the user's profile.

### Make the first admin
After registering your account, run this in the Supabase SQL editor, replacing the email:

```sql
update public.profiles
set role = 'admin'
where id = (select id from auth.users where email = 'YOUR_EMAIL');
```

Then sign out and sign back in. The Admin panel will appear.

## GitHub Pages
In GitHub: **Settings → Pages → Build and deployment → Source → GitHub Actions**. The included workflow deploys the root folder.

This project is for public information and community discussion only. It does not provide betting, wagering, deposits, withdrawals, or gambling predictions.