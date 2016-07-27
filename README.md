# jenkins-telegrambot
This is a command-line program to enable build notification.

## Requirements 
* Visual Studio 2015
* Telegram Bot ID
* Jekins build system (based window os)
 
## Jenkins configure & etc
* make a job "trigger post report telegram"
* add build param
  * Conditional step (single)
   * String match parameters 
  * Execute Windows batch command (BUILD_STATUS== SUCCESS)
   * \BuilderApps\TelegramBot\Telegram.Bot.Broadcasting "%BUILD_TRIGGER_NAME% @ SUCCESS @ %BUILD_ERROR_LOG%"
  * Execute Windows batch command (BUILD_STATUS== UNSTABLE)
   * \BuilderApps\TelegramBot\Telegram.Bot.Broadcasting "%BUILD_TRIGGER_NAME% @ UNSTABLE @ %BUILD_ERROR_LOG%"
  * Execute Windows batch command (BUILD_STATUS== FAILED)
   * \BuilderApps\TelegramBot\Telegram.Bot.Broadcasting "%BUILD_TRIGGER_NAME% @ FAILED @ %BUILD_ERROR_LOG%"
