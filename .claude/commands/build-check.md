# Build Check Command

Verify the site builds successfully and check for warnings or errors.

## Steps
1. Run `zola build` from the project root
2. Check the output for:
   - Compilation errors (template syntax issues)
   - Build warnings (orphaned assets, deprecated config)
   - Missing dependencies
3. If build succeeds:
   - Verify `public/` directory was created/updated
   - Report file count and total build size
4. If build fails:
   - Show the specific error message
   - Suggest fixes based on the error type
5. Report total build time

## Use This Command When
- Before committing changes
- After modifying templates or content
- After updating Zola version
- Ready to deploy to production
