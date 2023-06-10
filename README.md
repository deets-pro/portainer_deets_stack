# portainer_deets_stack

## Local development

1. Create stack.env file and put all environment variables there
2. `docker-compose up`

## Production

1. Go to Portainer
2. Go to stacks
3. Create a new github stack
4. put the url `https://github.com/deets-pro/portainer_deets_stack` and `refs/heads/main`
5. Add your environment variables
6. Deploy
7. Voila

## Troubleshooting

1. Local directory /home/deets/storage needs `chown -R 1000:1000 .`
2. You might need laravel clean up commands

    ```bash
    docker exec deets_laravel_php_v2 php artisan clear:data
    docker exec deets_laravel_php_v2 php artisan cache:clear 
    docker exec deets_laravel_php_v2 php artisan view:clear 
    docker exec deets_laravel_php_v2 php artisan route:clear 
    docker exec deets_laravel_php_v2 php artisan clear-compiled 
    docker exec deets_laravel_php_v2 php artisan config:cache
    docker exec deets_laravel_php_v2 php artisan key:generate (be cauctious with this one)
    docker exec deets_laravel_php_v2 php artisan storage:link
    docker exec deets_laravel_php_v2 php artisan migrate --seed (be cauctious with this one)
    ```
