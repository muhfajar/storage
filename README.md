# Storage

Sample code Cloudflare Worker to make your R2 bucket accessible from public.

## Minimum Requirements

1. Cloudflare Account
2. `wrangler >= 2.0.2`

**Note:** Ensure you are using at the minimum specified version of wrangler.

## Setup

1. Install dependencies (including Wrangler 2)

```bash
npm install
```

2. Create a bucket to be made public

```bash
wrangler r2 bucket create {{BUCKET_NAME}}
```

3. Update the `wrangler.toml` to bind the R2 bucket

```toml
[[r2_buckets]]
binding = 'PUBLIC' # <= make sure this var is valid JavaScript variable name
bucket_name = 'public'
```

4. Deploy the worker!

```bash
wrangler publish src/index.ts --name {{WORKER_NAME}}
```

5. Done 🎉

Give it a try: https://cdn.muhfajar.id/assets/glitch/v1/img/glitch.jpg
