# Bonus-task
@Composable
fun ListItem(
   input: Juice,
   onEdit: (Juice) -> Unit,
   onDelete: (Juice) -> Unit,
   modifier: Modifier = Modifier
) {
}
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.Arrangement
import com.google.accompanist.themeadapter.material3.Mdc3Theme

Mdc3Theme {
   Row(
       modifier = modifier,
       horizontalArrangement = Arrangement.SpaceBetween
   ) {

   }
}
JuiceIcon(input.color)
JuiceDetails(input, Modifier.weight(1f))
DeleteButton({})
DeleteButton(
   onDelete = {
       onDelete(input)
   },
   modifier = Modifier.align(Alignment.Top)
)@Preview
@Composable
fun PreviewListItem() {
   ListItem(Juice(1, "Sweet Beet", "Apple, carrot, beet, and lemon", "Red", 4), {})
}fun bind(input: Juice) {
    composeView.setContent {
        ListItem(
            input,
            onDelete,
            modifier = Modifier
                .fillMaxWidth()
                .clickable {
                    onEdit(input)
                }
                .padding(vertical = 8.dp, horizontal = 16.dp),
       )
   }
}
