# Jabbaar Life OS

System-ka maalinlaha ah ee web-ka.

## Supabase sync

Supabase SQL Editor-ka ku orod:

```sql
create table if not exists public.life_os_state (
  id text primary key,
  data jsonb not null,
  updated_at timestamptz not null default now()
);

alter table public.life_os_state enable row level security;

create policy "life_os_anon_access" on public.life_os_state
for all
using (true)
with check (true);

alter publication supabase_realtime add table public.life_os_state;
```

Dooro Settings → Supabase Project URL, Supabase anon/public key, iyo isla `Cloud ID` taleefanka iyo computer-ka.

`Cloud ID` waa sir: qof kastaa oo URL-ka, key-ga, iyo Cloud ID-ga ogaa wuxuu arki karaa/wax ka beddeli karaa xogta.
