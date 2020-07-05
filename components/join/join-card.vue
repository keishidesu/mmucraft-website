<template>
  <div>
    <div class="card-body p-4">
      <MCSubtitle>
        {{ item1.title }}
      </MCSubtitle>
      <div class="mt-3">
        Smash on this button to get your invitation link:
      </div>
      <div class="mt-3">
        <b-button variant="light" href="/invite">
          Get Invitation Here
        </b-button>
      </div>
      <div class="mt-3">
        {{ item1.desc }}
      </div>
    </div>
    <hr>
    <div class="card-body p-4">
      <MCSubtitle>
        {{ item2.title }}
      </MCSubtitle>
      <div class="mt-3">
        {{ item2.desc[0] }}
      </div>
      <div class="mt-3 text-danger">
        {{ item2.desc[1] }}
      </div>
      <div class="mt-3">
        {{ item2.desc[2] }}
      </div>
    </div>
    <hr>
    <div class="card-body p-4">
      <MCSubtitle>
        {{ item3.title }}
      </MCSubtitle>
      <div class="mt-3">
        {{ item3.desc[0] }}
      </div>
      <div class="mt-3">
        {{ item3.desc[1] }}<span class="text-info"> minecraft.mmu.edu.my</span>
      </div>
      <div class="mt-3">
        {{ item3.desc[2] }}
      </div>
    </div>
    <hr>
    <div class="card-body p-4">
      <MCSubtitle>
        {{ item4.title }}
      </MCSubtitle>
      <div class="mt-3">
        {{ item4.desc[0] }}
      </div>
      <div class="mt-3 text-info">
        {{ item4.desc[1] }}
      </div>
      <div class="mt-3">
        {{ item4.desc[2] }}
      </div>
    </div>
  </div>
</template>

<script>
import MCSubtitle from '~/components/mc/mc-subtitle'

export default {
  components: {
    MCSubtitle
  },
  data: () => {
    return {
      item1: {
        title: '1 - Getting the Invitation Link',
        desc: 'You need to provide a valid MMU email address in order to get the invitation link. After pressing the send button, go check your MMU email box. Within a few minutes, you should receive a MMUCraft email. Click on the button provided in the email will open up an account creation page.'
      },
      item2: {
        title: '2 - Creating an account',
        desc: [
          'On account creation page, enter your username and password. Finally, press on the create button.',
          'The username will use as your in-game username. Not only for login purposes. Moreover, there is no password confirmation input. Make sure you spelled your password correctly. If you make any mistake, please contact admins.',
          'If you have an existing official Minecraft username, it is recommended to use that name as our private server database is independant which has no connection with official Minecraft server.'
        ]
      },
      item3: {
        title: '3 - Joining the Server',
        desc: [
          'After you get everything installed, start the launcher. Note that you need internet the run the launcher for the first time. Make sure the username is matched as the one you registered and the game version is set to the correct version.',
          'Run Minecraft and in Multiplayer, click on Direct Connect, enter the following address:',
          'Click connect and you should be able to join the server.'
        ]
      },
      item4: {
        title: '4 - Login the Server (World)',
        desc: [
          'Once you get into the server, you cannot perform any action yet. Press "/" to and enter "/login" into the message box following by a space and your password. It should look something like this:',
          '/login mypassword123',
          'Press enter to execute. If your password is correct, you can now play the game.'
        ]
      }
    }
  }
}
</script>

<style>

</style>
