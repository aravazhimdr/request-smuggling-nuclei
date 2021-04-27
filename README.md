# HTTP Request Smuggling - Nuclei templates
 * Thanks to @pdnuclei for the template engine
 * These templates are prone to false positives
 * These templates try to identify smuggling via page comparison instead of timeouts
 * Best options - `nuclei -t ~/smuggling/ -concurrency 1 -bulk-size 10`
 * Less false positives - `cat subs.txt | httpx -x POST -ports 80,443 -status-code -silent -no-color | grep -v '\[400\]\|\[404\]\|\[501\]\|\[503\]\|\[504\]' | nuclei -t ~/smuggling/ -concurrency 1 -bulk-size 10`
