# Missing binary links with aliased PostCSS 7 compatibility build
Reproduction repo for https://github.com/tailwindlabs/tailwindcss/issues/4966

Tailwind docs suggest installing the PostCSS 7 compatibility build as aliased package:

`npm install -D tailwindcss@npm:@tailwindcss/postcss7-compat`

When I do this, there are no binary links created for Tailwind in node_modules/.bin, so the cli is not usable.
The command `npm run help` will fail.

Without aliasing the package, the links (tailwind / tailwindcss) are created:

`npm install -D @tailwindcss/postcss7-compat`

So for now I go with a combination of both:

`npm install -D tailwindcss@npm:@tailwindcss/postcss7-compat @tailwindcss/postcss7-compat`

This works, but feels weird of course. Why aren't the links created using only the aliased package?